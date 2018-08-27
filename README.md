# nagios-check-phishtank Nagios plugin to check the Phishtank database for a string

Features
--------

This plugin downloads the Phishtank database in CSV and checks it for a string.

The database is only refreshed every 60 minutes (by default), so it is safe to run the check script frequently (eg. against many domains).

There is no need to check for a fully qualified domain name. If your domain names is www.example.org, it is safe to search 'example' or 'example.org'.


Requirements
------------

Bash (or compatible) shell


Configuration
-----

The configuration variables at the top of the script determine:

* where to store the downloaded CSV database (tmp_folder)
* how frequently to refresh the CSV database (file_expiry_mins)
* Phishtank API key (phishtank_api_key)

The Phishtank API key can be obtained for free at: https://www.phishtank.com/api_register.php. It is possible to operate the script without the API key, but the number of times per day the database may be downloaded will be restricted. Refer to Phishtank's [Developer Info page](https://www.phishtank.com/developer_info.php) for details.


Usage
-----

Syntax:

	check_phishtank <search string>

`<search string>` is the domain (or part thereof) to check the Phishtank database for
