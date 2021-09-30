Silverstripe Facebook App
=========================
Connect your silverstripe website to a Facebook application. This module uses the graph API.

This is in the alpha stage and currently only posts to walls of pagebook fan pages. However, I plan to add other features of the graph API later.

You will need to have signed up for Facebook developers and created an app to use this module.

Installation
------------
* Setup the configuration file with your facebook applications keys. 

        //Facebook API
        //Enable the module, comment this out to leave the module disabled.
        FacebookModule::enable();
        //Set the application id
        FacebookModule::set_application_id('22xxxxxxxxxxxx');
        //Set the application secret key
        FacebookModule::set_app_secret('c7afxxxxxxxxxxxxxxxxxxxxxxxxxxxx');
        //Set the api key
        FacebookModule::set_api_key('34xxxxxxxxxxxxxxxxxxxxxxxxxx');
        //Set the page_id. upDateStatus will post to this page.
        FacebookModule::set_page_id('12xxxxxxxxxxxx');

* Finally, log into the Facebook account that owns the page. Go to site configuration. Click the link to authorize your website with Facebook. To do this, the website must be live and on the same URL specified in your application settings.

* Facebook will ask for permission to post to your wall at any time. Click accept. It would be best if you were taken back to the administration page. The website is now permitted to post to your Facebook wall.


Usage
-----

### Post to page wall

    $params['description'] = $summary;
    $params['link'] = Director::absoluteBaseURL() . 'go/' . $tracked_link->Slug;
    $params['picture'] = $this->Image()->getAbsoluteURL();
    FacebookModule::updateStatus($params);
