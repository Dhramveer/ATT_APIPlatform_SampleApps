******************************************************************************************
* Licensed by AT&T under 'Software Development Kit Tools Agreement.' 2012
* TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION: http://developer.att.com/sdk_agreement/
* Copyright 2012 AT&T Intellectual Property. All rights reserved. http://developer.att.com
* For more information contact developer.support@att.com<mailto:developer.support@att.com>
******************************************************************************************

  AT&T API Platform Samples - Call Control App 1
 -----------------------------------------------
This API provides operations to support the creation of outgoing call Sessions 
and Signals to existing sessions. Incoming calls sessions will be created 
automatically in the call environment.

This file describes how to set up, configure and run the VB.NET Applications of the
AT&T API Platform sample applications. It covers all steps required to register
the application on DevConnect and, based on the generated API keys and secrets, 
create and run one's own full-fledged sample applications.

  1. Configuration
  2. Installation
  3. Parameters
  4. Running the application


1. Configuration

  Configuration consists of a few steps necessary to get an application registered
  on DevConnect with the proper services and endpoints, depending on the type of
  client-side application (autonomous/non-autonomous). 

  To register an application, go to https://devconnect-api.att.com/ and login with
  your valid username and password. Next, choose "My Apps" from the bar at the top
  of the page and click the "Setup a New Application" button. 

  Fill in the form, in particular all fields marked as "required".

  Be careful while filling in the "OAuth Redirect URL" field. It should contain the
  URL that the oAuth provider will redirect users to when he/she successfully
  authenticates and authorizes your application.

NOTE: You MUST select Call Control in the list of services under field 'Services'
in order to use this sample application code. 

  Having your application registered, you will get back an important pair of data:
  an API key and Secret key. They are necessary to get your applications working with
  the AT&T Platform APIs.

  Initially your newly registered application is restricted to the "Sandbox"
  environment only. To move it to production, you may promote it by clicking the
  "Promote to production" button. Notice that you will get a different API key and
  secret, so these values in your application should be adjusted accordingly.

  Depending on the kind of authentication used, an application may be based on either
  the Autonomous Client or the Web-Server Client OAuth flow (see
  https://devconnect-api.att.com/docs/oauth20/autonomous-client-application-oauth-flow or
  https://devconnect-api.att.com/docs/oauth20/web-server-client-application-oauth-flow
  respectively).



2. Installation

** Requirements

   To run the this sample application you need an IIS Server. 

   Download the application files from the download link published in AT&T portal
   into webdomain of your IIS server.



3. Parameters
   
Each sample application contains a web.config file. It holds configurable parameters
described in an easy to read format. Please populate the following parameters in
web.config as specified below:

1) apiKey                	: This is mandatory parameter, set the value as per 
				  your registered appliaction 'API key' field value.

2) secretkey     	  	: This is mandatory parameter, set the value as per
				  your registered appliaction 'Secret key' field value.

3) endPoint			: This is mandatory parameter, set it to the end point
				  URI of AT&T Service.

4) scope			: CCS (Scope of the ATT service that will be invoked by
				  the Application)

5) AccessTokenFilePath		: ~\\CCSApp1AccessToken.txt (This is optional parameter, 
				  which points to the file path, where application stores 
				  access token information. If the parameter is not 
				  configured, it will take the default value as 
				  ~\\CCSApp1AccessToken.txt.
			  	  Give read/write access to this file.)

6) phoneNumbers			: This is mandatory key, which specifies the registered phone numbers 
			          for this application.

7) refreshTokenExpiresIn	: This is optional key, which specifies the expiry time of refresh 
 				  token in Hrs. Default value is 24Hrs.


Note: If your application is promoted from Sandbox environment to Production environment
and you decide to use production application settings, you must update parameters 1-2
as per production application details.



4. Running the application

Suppose you copied the sample app files in your IIS server webroot/callcontrol/app1/ folder.
In order to run the sample application, type in'http://IIS_HOSTNAME/callcontrol/app1/Default.aspx'.
