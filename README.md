odi-11g-password-decoder
========================

Oracle Data Integrator 11g Password Decoder

The purpose of this application is simple. ODI stores all related passwords (odi login, db passwords)
file "snps_login_work.xml" under user profile (eg. c:\users\odi_user\AppData\Roaming\odi\oracledi\snps_login_work.xml)

There are all passwords encoded in this file and stored in following XML elements:

<Field name="LoginPass" type="java.lang.String"><![CDATA[ENCODED_PASSWORD]]></Field>
<Field name="LoginDbpass" type="java.lang.String"><![CDATA[ENCODED_PASSWORD]]></Field>

Usage:
Copy and paste encoded passwords from XML file and paste into input text box in application, click decode.

Oracle intended to store the passwords in some more secure way, which has been done somehow, the older versions of ODI
stored passwords in plain text and were not accepted by security architects... Now they are accepted, however the 
decoding process is quite simple:
- link odi-core.jar library to your project
- import com.sunopsis.dwg.DwgObject object
- call static DwgObject.snpsDecypher(ENCODED_PASSWORD);

That's it.

NOTE: There is generated EXE application binary for Microsoft Windows OS.
