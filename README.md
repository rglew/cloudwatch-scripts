cloudwatch-scripts
==================

Ansible role for installing and configuring ansible cloudwatch scripts for linux

The scripts that are included are from [Amazon's CloudWatch Scripts for Linux](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/mon-scripts-perl.html) page.  These are Perl scripts, hence the need to install Perl..

It's possible to download the scripts directly from Amazon as part of the play of course, but in this case I have chosen to push them up into S3 to be certain the play will always run as expected.  The Python and Boto installs are required for the Ansible S3 module to work.

The other thing about the S3 module is that you need to pass some AWS credentials through to the target server to access S3 (unless you have implemented IAM machine roles instead) which in this case is achieved by looking up the appropriate environment variables on the host to avoid having to log AWS keys in a file somewhere.

It's being run as the default ubuntu user who has passwordless sudo permissions - this may or may not be an issue for you!

