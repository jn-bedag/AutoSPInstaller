# AutoSPInstaller
Automated SharePoint 2010/2013/2016/2019/SE PowerShell-based installation script.


# Forked

This project was forked and we made some improvements/changes to meet our requirements, mostly according to SSL certificates.  
Be aware that the changes are not tested in all scenarios, so use at your own risk.

# Changes/Improvements

- Improvement: The script now also looks for an existing certificate in certstore which matches the dns-name.
- Improvement: If you have multiple ssl sites listening on the same port, the script configures (Server Name Indication) SNI.
- Improvement: Provide a new parameter -logPatch which let's you specify a custom log directory instead the useres desktop.
- Improvement: Improved checking for default web site. Script broke if there was no default web site.
- Change: Don't start all the URLs in browser after installation.
- Fix: If you have manually added additional Search ContentSources, the script was failing.
- Fix: Implemented error handling for site creation if it fails.

We run the script from admin PowerShell:  
.\AutoSPInstallerMain.ps1 -inputFile .\inputfile.xml -logpath C:\install

