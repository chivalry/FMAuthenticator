# FMAuthenticator

FMAuthenticator is a technique for implementing two-factor authentication (2FA) in the
FileMaker database platform.

The demo database that is included in this zip file serves as both an example of the
technique as well as a method for delivering the FileMaker table and script that it uses.

## FileMaker Accounts

The demo file includes a single FileMaker account:

Account Name: admin
Password: FM2FA-admin
Privilege Set: Full Access

## Configuring the Demo Database

To see FMAuthenticator in action, configure the demo database as follows:

- Open the FMAuthenticator script, and add your SMTP server settings. If you do not have
an SMTP server available, you might consider using Mandrill, is an email infrastructure
service. The first 12,000 emails sent per month are free. For details, visit:
http://mandrill.com

- Take a moment to review the Send Mail script step. In particular, review the SMTP
Server settings and be sure that they are configured so that FileMaker can communicate
and authenticate with your SMTP server.

- Switch to the FMAuthenticator layout, and for the "admin" record, enter your email
address. If you would like to receive the two-factor authentication codes as a text
message, then enter your SMTP gateway address. For assistance, please see the "SMS
Gateway Information" page on the http://fmauthenticator.com Web site. Also note that you
if you would like to have the codes sent to multiple addresses, enter them in the
Email_Address field, separated by commas.

That's all there is to it. When you are finished, log into the database.

## Wiring up FMAuthenticator to Your Own Solution

For details on how to add FMAuthenticator to your database, please see the "Setup and
Configuration" page on the FMAuthenticator Web site: http://fmauthenticator.com

## Support

For technical support, please first take a look at the "Troubleshooting" and "Setup and
Configuration" pages on the FMAuthenticator Web site: http://fmauthenticator.com

If you need additional support, or have questions about FMAuthenticator, please feel free
to contact me:

Tim Dietrich  
E-Mail: timdietrich@me.com  
Web: http://timdietrich.me  
Twitter: @tdietrich
