# FMAuthenticator: Frequently Asked Questions

## What is two-factor authentication?
Two-factor authentication is a technique that is used to confirm the identity of users.
It requires users to provide two forms (or “factors”) of identification. Those two
factors are sometimes described as being “something the user knows” and “something the
user has.” In other words, something that they’ve memorized (such as their account name
and password) and something physical that they have in their possession (such as a mobile
phone).

## Why would I want to use two-factor authentication with FileMaker?
Two-factor authentication further enhances the security model that FileMaker provides
natively. It requires that users provide additional information - information that, in
theory, only they have access to. As a result, it makes your databases even more secure
than they normally are.

## What is involved in setting up FMAuthenticator?
The setup process is relatively straightforward. [Click here](setup.php) for complete
instructions.

## Does FMAuthenticator require any FileMaker plugins?
No. FMAuthenticator uses only native FileMaker functions, so no plugins are needed.

## Does FMAuthenticator involve the use of Web services?
No. FMAuthenticator sends authentication codes via email, using an SMTP server that you
specify.

## Do I need to setup my own SMTP server?
No. Chances are that you already have access to an SMTP server, either through your
hosting company or IT department. Another option - and one that we've had a lot of
success with - is to use an email service such [Mandrill](http://mandrill.com). (For
details on how to configure FMAuthenticator for use with Mandrill, refer to [this blog
post](http://www.timdietrich.me/blog/fm-authenticator-with-mandrill/).)

## Is a demo database available?
Yes, and you can [download it here](download.php).

## What versions of FileMaker are supported?
FMAuthenticator works with the FileMaker 12 and 13 platforms, including FileMaker Pro,
Pro Advanced, and Go.

## Does FMAuthenticator work with WebDirect?
Yes. FMAuthenticator can be used to authenticate WebDirect users.

## Does FMAuthenticator work with databases that are stored locally?
Yes. You can use FMAuthenticator with both hosted and local databases.

## How does FMAuthenticator send authentication codes?
FMAuthenticator sends authentication codes as email messages using the FileMaker "Send
Mail" script step, and through the SMTP server that you specify. You can send
authentication codes to a user's mobile device as a text message by sending an email
message to the user's SMS gateway address.

## Do you have information about SMS gateway addresses?
Yes, we have a list of 300 cellular carriers and their Mail-to-SMS gateways. [Click
here](sms-gateways.php) to view the list.

## Wasn't FMAuthenticator originally going to be a paid service?
Yes, it was. To learn why we decided to make FMAuthenticator an open source solution, see
[this blog post](http://www.timdietrich.me/blog/fm-authenticator-two-factor
authentication-for-filemaker-v2/).

## How much does FMAuthenticator cost?
Nothing. FMAuthenticator is being provided via an open source license. You'll find a copy
of the license in the FMAuthenticator zip file.

## Are there are any potential costs that I should be aware of?
Yes. If you are sending authentication codes to users as text messages, then standard
text messaging rates may apply, depending on the plan that a user has with their mobile
service provider.

## Can I setup a user so that their authentication codes are sent to multiple devices?
Yes. To do so, add a record to the FMAuthenticator table, specifying their Account Name.
Then set the Email_Address field so that the multiple addresses are separated by a comma.
For example: test@example.com, 5555551212@txt.att.net

## Can I setup a user so that their authentication codes are sent to an email address?
Yes. You can send the authentication codes to email addresses and Mail-to-SMS gateway
addresses.

## Can I setup certain users so that they are not required to go through the two-factor authentication process?
Yes. In the FMAuthenticator table, setup a record for them, and set the Allow_Bypass
field to a value of 1\. Another option is to configure FMAuthenticator so that the
"unknown_user_behavior" setting is set to "Bypass," and then only add records to the
FMAuthenticator table for users that you do want to authenticate.

## Can I indicate what should happen if the SMTP server is down?
Yes. Using the "smtp_error_behavior" setting (in the FMAuthenticator script), you can
allow users to bypass the two-factor authentication process if the SMTP server is
unavailable, or when the attempt to send a message through it returns an error. See the
[Setup](setup.php) page for more information.

## Can I limit the number of attempts that a user can make?
Yes. By default, if a user enters three incorrect authentication codes, the database will
close, and they will need to log back into the database to try again. You can use the
"max_attempts" setting (in the FMAuthenticator script) to adjust the number based on your
preference.

## Can I control the length of the authentication codes?
Yes. By default, the codes are 4-digit numbers. You can use the "code_length" setting (in
the FMAuthenticator script) to increase or decrease the size.

## Is it possible for some users to bypass FMAuthenticator?
Yes. Users who have Full Access privileges, and that are running FileMaker Pro Advanced,
can potentially circumvent the two-factor authentication process. Using the Data Viewer,
it is possible for the Full Access user to see the authentication code that is generated.
Unfortunately, this is simply how FileMaker Pro Advanced works, and there isn't much we
can do about it.

## Who developed FMAuthenticator?
FMAuthenticator was developed by Tim Dietrich, a database consultant that develops custom
databases using the FileMaker platform. To learn more about Tim, visit his Web site:
[timdietrich.me](http://timdietrich.me)
