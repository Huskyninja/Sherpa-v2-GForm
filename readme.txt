=== Plugin Name ===
Plugin Name: Sherpa v2 GForm
Description: Send form data to the Sherpa CRM's v2 endpoint using Gravity Form's Add-on Framework
version: 0.5
Author: Husky Ninja
Author URI: https://www.husky.ninja
License: GPLv3 or later
Text Domain: sherpa_v2_gform
Domain Path: /languages

== Description ==

Important: This plugin is an early alpha.
If you intend to use this in a production environment, please alert the development team. Also be sure to report any issues or unexpected behaviors promptly.

For use only with Gravity Forms v1.9 or greater.

Main Settings

Main for settings can be found under admin -> Forms -> Settings -> Sherpa v2 GForm. You will need a the Company ID and Authentication Key supplied by Sherpa. The sandbox Company ID and Authentication Key are set by default. You will need the correct values supplied by Sherpa.

The base endpoint url is also set to the sandbox environment by default. The production endpoint url is https://members.sherpacrm.com/v1. This value is used to construct the full endpoint url using the Company and Community IDs. Please do not use any trailing slashes.

If you wish to send a debug email select the "Send a debug email" checkbox. The debug email contains the json query and the response from sherpa, and is useful in debugging without the presence of a log file.

Enter a single valid email into the "Debug email address" field. Invalid email addresses will not send a debug email.

If necessary, set the Sherpa Autoset Values for the fields that are required by Sherpa to process the request. This is a global setting, but it can be overwritten by mapping the appropriate fields at the form level (see Field Mapping, below).

The default values for the Sherpa Autoset Values should be correct for 99% of requests sent.

Form Settings

Individual form settings can be found under admin -> Forms -> Forms -> {form name} -> Settings -> Sherpa v2 GForm.

Select the "Send this form to Sherpa" checkbox to attach the form. The Community ID is set to the sandbox Community ID by default. You will need a Community ID supplied by Sherpa.

By default this plugin uses Remote Post (wp_remote_post) to send form data. This can be changed to to use cURL. If you have cURL installed and wish to use this method, select this checkbox.

Field Mapping

To map the form fields, select the relevant Field (to be mapped for Sherpa) to the Form Field (from the Gravity Form). Some field values are set by the Sherpa Autoset Values (above), but may be overwritten here.

The form field must be of the correct type. The mapping is as follows:

First Name -> name, text or hidden
Last Name -> name, text or hidden
Email Address -> email or hidden
Phone -> phone or hidden
Vendor Name -> hidden
Source Category -> hidden
Source Name -> hidden
Advisor Referral Note -> hidden, textarea or select
Resident First Name -> hidden or text
Resident Last Name -> hidden or text
Resident Relationship -> hidden or select

So make sure when creating your form that you use the correct form field types for the Sherpa field mapping.

For more information on field mapping, see the Sherpa v2 GForm plugin page under Forms in the Admin Console.

== Changelog ==

= 0.5 =
* updated author info now that sage age no longer supporting module
* finally fixed scripts and styles
* added placeholder in the languages directory

= 0.4 =
* changed default method for posting to Wordpress Remote Post with cURL as a selectable alternative

= 0.3 =
* updated help docs to include production url

= 0.2 = 
* Removed commented code related to v1 of the API
* Added target as part of debug email
* Fixed issue with quick set drop down values for primaryContactResidentRelationship causing firstName and lastName values to me incorrectly formatted by the server

= 0.1 =
* First buildout.

== Upgrade Notice ==

= 0.0 =
Placeholder.

== Arbitrary section ==

This is arbitrary.