rails_locales_generator
=======================

simple generator to create Rails 3+ i18n locales for active record models and active view helpers 

http://guides.rubyonrails.org/i18n.html

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

Just clone the project and copy the generators folder to your rails 3+ project.

Now you can use the locales generator in your rails 3+ project folder.

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