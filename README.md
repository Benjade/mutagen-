# mutagen
Mutagen+

For those interested, I've corrected the Mutagen version so that it takes into account the first prefix of the range zone, so there's no resource waste. 
I've also added a function to send an email when a key is found, as it's always good to be informed directly if you have multiple servers. 

Mutagen now displays the progress of each thread to verify that the keys are correct.

Simply replace this version with the old one and change the email address to yours in the script. It uses MSMTP for sending emails, but you can replace it with /usr/sbin/sendmail or something else if you prefer.

If you want to use MSMTP:

`sudo apt install msmtp msmtp-mta -y`

`sudo nano /etc/msmtprc`

Add this and change by your email account:


defaults<br>
auth           on<br>
tls            on<br>
tls_starttls   on<br>
tls_trust_file /etc/ssl/certs/ca-certificates.crt<br>
logfile        /var/log/msmtp.log<br>
account        default<br>
host           smtp.gmail.com<br>
port           587<br>
from           your@gmail.com<br>
user           your@gmail.com<br>
password       yourpassword<br>

-----------

Test if email work:

`echo "This is a test." | msmtp your@email.com`

Good luck!
