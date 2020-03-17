=== Plugin Name ===
Plugin Name: Sherpa v2 GForm
Description: Send form data to the Sherpa CRM's v2 endpoint using Gravity Form's Add-on Framework
version: 0.4
Author: Sage Age
Author URI: https://www.sageagestrategies.com/
License: GPLv3 or later
Text Domain: sherpa_v2_gform
Domain Path: /languages

== Description ==

Important: This plugin is an early alpha.
If you intend to use this in a production environment, please alert the development team. Also be sure to report any issues or unexpected behaviors promptly.

For use only with Gravity Forms v1.9 or greater.

Main Settings

Main for settings can be found under admin -> Forms -> Settings -> Sherpa v2 GForm. You will need a the Company ID and Authentication Key supplied by Sherpa. The sandbox Company ID and Authentication Key are set by default. You will need the correct values supplied by Sherpa.

The base endpoint url is also set to the sandbox environment by default. This value is used to construct the full endpoint url using the Company and Community IDs. Please do not use any trailing slashes.

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

First Name -> textfield
Last Name -> textfield
Email Address -> email
Phone -> phone
Vendor Name -> hidden
Source Category -> hidden
Source Name -> hidden
Advisor Referral Note -> hidden, textarea or select
Resident First Name -> hidden or textfield
Resident Last Name -> hidden or textfield
Resident Relationship -> hidden or select
So make sure when creating your form that you use the correct form field types for the Sherpa field mapping.

Sherpa Field Mapping Information

Below is a table of how fields map with this add on. Please refer to your Sherpa documentation for more information.

Addon Field Name		Sherpa Field Name					Required By Sherpa		Main Settings Autofill
First Name				primaryContactFirstName				Yes						No
Last Name				primaryContactLastName				Yes						No
Email Address			primaryContactEmail					No						No
Phone					primaryContactHomePhone				No						No
Vendor Name				vendorName							Yes						Yes
Source Category			sourceCategory						Yes						Yes
Source Name				sourceName							Yes						Yes
Advisor Referral Note	advisorReferralNote					No						No
Resident First Name		residentContactFirstName			Yes						Yes
Resident Last Name		residentContactLastName				Yes						Yes
Resident Relationship	primaryContactResidentRelationship	No						Yes

== Changelog ==

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
