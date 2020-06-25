# AutoSPInstaller
Automated SharePoint 2010/2013/2016/2019 PowerShell-based installation script.

This project was migrated to GitHub from CodePlex, where it was downloaded over 130,000 times!

Love AutoSPInstaller? Has it saved you or your company time and money? Have you used it in any of your or your customers' projects or deployments? If so, why not consider [donating](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=QQPQPFRUTVWJJ&lc=CA&item_name=Brian%20Lalancette%27s%20Github%20Projects:&item_number=AutoSPInstaller&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donate_LG%2egif%3aNonHosted") towards its ongoing support and development!

# Forked

This project was forked and we made some improvements/changes to meet our requirements, mostly according to SSL bindings.  
We now can terminate SSL on the sharepoint servers, provide certificates from an PKI and have an http to https redirect.  
- Change: If for a webapplication SSL and port 443 are specified, also create an http port 80 binding and add the alternate access mapping. This allows to have an redirect from http to https
- Improvement: The script now also looks for an existing certificate in certstore witch matches the dns-name
- Improvement: Provide a new parameter -logToScriptDir which saves the AutoSPInstaller log to the scripts \log directory.
- Improvement: Improved checking for default web site. Script broke if there was no default web site.
- Change: Don't start all the URLs in browser after installation
- Fix: Install prerequisites also for newer server Version
- Fix: The script was checking for the wrong url when creating the webapp

We run the script from plain admin PowerShell:  
.\AutoSPInstallerMain.ps1 -inputFile .\inputfile.xml -logToScriptDir

Be aware that the changes are not tested in all scenarios, so use at your own risk.