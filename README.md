## monitor2mail - script to monitor list of url (https/http/ns/mx) and send mail if down
***

monitor2mail - script to monitor list of url (https/http/ns/mx) and send mail if down


## Installation

Please first clone repository :

    git clone https://github.com/bkittler/monitor2mail

    cd ./cmonitor2mail

And install Python and requirements :

    pip3 install -r requirements.txt


create txt file containing url to monitor and email.
see example : url_monitored.txt

Open monitor2mail.py and complete variables :

    smtp_address = 'smtp.domainmail.com'
    
    smtp_port = 465

    email_address = 'EMAIL@EMAIL.COM'

    email_password = 'PASSWORD'

## Usage

There are three launch modes :

* -t or --test for test : Display of tests, no mail send

* --debug : Full display of tests , no mail send

* just file : Sending mail if one url is DOWN, no display


Test mode synthax:

	monitor2mail.py url_monitored.txt --test

or 

	monitor2mail.py url_monitored.txt -t

Production synthax (email send when one host is DOWN):

	monitor2mail.py url_monitored.txt

Debug mode synthax:

	monitor2mail.py url_monitored.txt --debug


## Crontab

If you want to monitor host, you can add script on crontab (example every 2 min):

	*/2 * * * * /usr/bin/python3 /home/user/monitor2mail/monitor2mail.py /home/user/monitor2mail/url_monitored.txt


## Warning

This script need Python3 and dnspython.

if import dns displays an error, please make :
	
	git clone https://github.com/rthalley/dnspython
	
	cd dnspython/

	python setup.py install

If you have an error : certificate verify failed: unable to get local issuer certificate (_ssl.c:1045),
on python directory please install :

	Install Certificates.command
	

All entry must be unique on file. Second same entry is ignored.

## Dependencies

please install python dependancies before run tool :

    pip install -r requirements.txt

## Further information and help

GitHub has an excellent [documentation](https://help.github.com/). Check it out if you need help!

For further questions please contact [Kittler](https://www.kittler.fr/).

