rails_locales_generator
=======================

A Rails 3+ generator that creates the i18n locales files for active record models and action view helpers (i.e., submit & button). 

Read over http://guides.rubyonrails.org/i18n.html if you haven't already.

The locales generator will create a folder structure in your project's config/locales folder like the following for a rails project with an existing model named campaign and a campaigns resource controller:

<pre>
|-models
|---campaigns
|-----en.yml
|-views
|---campaigns
|-----en.yml
</pre>

Get started
===========

Just clone the project and copy the generators folder to your rails project.

Now you can use the locales generator in your rails 3+ project folder.

For example, say you have a campaign model and campaigns resource controller in your project:

```shell
rails g locales campaigns
```

Here's what it would create:

- config/locales/models/campaigns/en.yml

<pre>
en:

  activerecord:
    models:
      campaign: "Campaign"

    attributes:
      campaign:
        name: "Name"
        description: "Description"
        active: "Active"

    errors:
      models:
        campaign:
          attributes:
            name: "Name"
            description: "Description"
            active: "Active"
</pre>

- config/locales/views/campaigns/en.yml

<pre>
	en:

	  navigation:
	    campaigns: "Campaigns"

	  helpers:

	    submit:
	      campaign:
	        create: "Add Campaign"
	        update: "Update Campaign"

	    button:
	      campaign:

	  messages:
	    campaigns:
	      created: "Campaign has been created."
	      updated: "Campaign has been updated."
	      none: "There are no Campaigns yet. Click 'New Campaign' to get started."

	  campaigns:

	    links:
	      back_to_index: "Back to Campaigns"

	    index:
	      title: "Campaigns"
	    new:
	      title: "New Campaign"
	    edit:
	      title: "Edit Campaign"
	    show:
	      title: "Campaign"	
</pre>

Next, ensure you have the models and views locales auto loaded in your environment.

Here is an example of how to load the models and views locales in the
config/application.rb:

```ruby
     models = Dir[Rails.root.join('config', 'locales', 'models', '**/*.yml').to_s]
     views  = Dir[Rails.root.join('config', 'locales', 'views', '**/*.yml').to_s]

     config.i18n.load_path += models + views
````
	