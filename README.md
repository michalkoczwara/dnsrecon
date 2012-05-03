##Version 0.7.3

###Date: 5/2/12
###Changes:
- Fixes for Python3 compatibility.
- fix key values for when saving results to XML and CSV.

##Version 0.7.0

###Date: 3/2/12
###Changes:
- Fixes to Zone Walk option.
- Query for _domainkey record in standard enumeration.

##Version 0.6.8

###Date: 2/15/12
###Changes:
- Added tool folder with python script for parsing results in XML and CSV format. Provide ability to filter and extract hostnames and subdomains.
- Added Metasploit Plugin for importing in to metasploit the CSV and XML results in a very fast manner using Nokogiri for XML, it ill add hosts, notes for hostnames and service entries.
-Improvements on the zone transfer code:
	
	- Handling of zones with no NS Records.
	- Proper parsing of PTR Records in returned zones.
	- De-duplication of NS record IP Addresses.
	- Provide additional info on failure.
	- Provide more infomation on actions being taken.

- Bug fixes reported by users at RandomStorm and by Robin Wood.
- Zone Walking has been greatly improved including the accuracy of the results and the formatting to extract the information in a manner more useful for a pentester. 

##Version 0.6.6

###Date: 1/20/12
###Changes:
- Does not for a Origin Check for zones transferred since some admin may have configured their zones without NS Servers as experienced by a user.
- Handles exception if NS records cannot be resolved when performing a zone transfer test.
- Will always for a test for the SOA and test it for zone transfer.
- Fixed problem when generating an XML from a zone transfer with the new parsing method, info type was added to the XML output.

##Version 0.6.5
###Date: 1/16/12
###Changes:
- Fixed problem with get_ns.
- Python 3.2 support.
- Color printing of messages like Metasploit.
- New library for printing color messages.
- Improved parsing of records when it is a zone transfer.

##Version 0.6.1
###Date: 1/14/12
###Changes:
- IPv6 support for ranges in reverse look-up.
- Enhanced parsing of SPF records ranges to cover includes and IPv6.
- Specific host query for TXT RR.
- Better handling and logging of TXT and SPF RR.
- Started changes for Python 3.x compatibility.
- Filtering of wild-card records when saving brute-force  results.
- Show found records after brute-force of domains is finished.
- Manage Ctrl-C when doing a brute-force and save results for those records found.
- Corrected several spelling errors.

##Version 0.6
###Date: 1/11/12
###Changes:
- Removed mDNS enumeration do to that the pybonjour library has been abandoned and faster ways are available to achieve enumeration of mDNS records in a sub-net.
- Removed un-used variables.
- Applied changes for PEP8 compliance.
- Added comma delimited value to a file for the results.

##Version 0.5.1
###Date: 1/8/12
###Changes:
- Additional fixes for XML formatting.
- ability to end a zone walk with control-c and not lose data.
- Initial Metasploit plug-in to be able to import data from XML file generated by dnsrecon.

##Version 0.5
###Date: 1/8/12
###Changes:
- Will check in standard enumeration is DNSSEC is configured for the zone by checking for DNSKEY Records and checking is the zone is configured as NSEC or NSEC3.
- With the get_ip() method it will also check for CNAME records and add those to the list found hosts.
- Will Perform a DNSSEC Zone Walk if NSEC Records are available, it identifies currently A, AAAA, CNAME, NS and SRV records any other it will just print the RDATA info.
- General record resolver method added.
- Changes to the options.

Known Issues:
- For some reason the python getopt is not parsing the options correctly in some cases. Considering changing to optparse even if it is  more complicated to manage.
- When Running on version 3.x of Python the Whois wuery does not show the organization.

