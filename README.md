# Wordpress Activities
##Objective
Create web page using Wordpress
##Method
###Prior to 2015 09 30
####Get Domain Name
* Get domain name from Namecheap.
  * one year $10.69
  * `worksatscale.com`
  * Positive SSL for `www.worksatscale.com` $1.99 first year
  * free WhoisGuard

####Get Shared Hosting
* Get shared hosting from Namecheap
  * $9.88/first year
  * 20GB SSD disk
  * unlimited bandwidth
  * up to 3 websites

####Set Up Wordpress
#####Wordpress Local Setup
* Install XAMPP
  * [Download](https://www.apachefriends.org/download.html)
  * [Install details](https://www.apachefriends.org/faq_linux.html)
    * `cd /opt/lampp/`
    * `chmod 755 manager-linux-x64.run`
    * `sudo ./manager-linux-x64.run`
    * GUI `sudo ./manager-linux-x64.run`
* Config Apache HTTPD to Listen on port `1337`
* Start Apache and MySQL
* Create database
  * Open XAMPP Control Panel
    * Open `localhost:1337` since that's the port we're listening on 
    * `phpMyAdmin` on top nav bar
  * Select Database admin function on nav bar
  * Create database `wp`
  * Set Collation option as utf8_unicode_ci. But see [utf8mb4](https://dev.mysql.com/doc/refman/5.5/en/charset-unicode-utf8mb4.html), which implies `utf8mb4_unicode_ci` is more appropriate.
  * Download [Wordpress](https://wordpress.org/download/)
  * `sudo cp -r ~/Downloads/wordpress /opt/lampp/htdocs/`

###2015 09 30
* Navigate to [localhost:1337/wordpress](http://localhost:1337/wordpress)
* Wordpress initial config from dialog page
  *  DB Name: `wp`
  *  MySQL username: `root`
  *  DB password: ``
  *  DB host: `localhost`
  *  table prefix: `wp_1` *Note:* Not in video
  *  bad permissions
  *  [How to fix permission of htdocs in Ubuntu](http://computernetworkingnotes.com/ubuntu-12-04-tips-and-tricks/how-to-fix-permission-of-htdocs-in-ubuntu.html)
  *  `sudo chown -R rjhintz:rjhintz /opt/lampp/htdocs`
  *  manually edit
  *  Run install
    * Site title: `works at scale test`
    * username: `rjhintz`
    * password: `OmX@lRJi7j0YZms(Pf`
    * email: `rjhintz@gmail.com`
    * allow search engines: No
  * Log in with userid/pw
  * Wordpress 4.3.1; Twenty Fifteen theme
  * `http://localhost:1337/wordpress/wp-admin/`
  
###2015 10 04
*  Reinstall Wordpress, want to anchor at `www.worksatscale.com` not `www.worksatscale.com/wordpress`
*  Note: info on redirecting from `wordpress` install directory to site root uses Apache file `.htaccess` that's currently in Akismet plugin
*  Install in Web Root directory for now
*  Update current plugins (Akismet)
*  Delete `Hello Dolly` plugin
*  Install new plugins
  * Jetpack
  * All in One SEO Pack
  * SEO Friendly Images
  * Google XML Sitemaps
  * W3 Total Cache
  * iThemes Security
  * UpdraftPlus Backup and Restoration
  * Wordpress Zero Spam
  * Stop Spammers Spam Prevention
  * Favicon by RealFaviconGenerator
* Restart XAMPP services for local site (to allow copy/paste content from local site)
  * Apache web server
  * MySQL DB
* Jetpack config
* W3 Cache config
* Stop Spammers config
  * Get [Google Safe Browsing API Key](https://developers.google.com/safe-browsing/key_signup)
* Set up `info@worksatscale.com` and forwarding
* set up [CloudFlare CDN](https://server118.web-hosting.com:2083/cpsess8050042956/frontend/x3/cloudflare/index.html) through Namecheap
  * Apparently kills https using free, partner with Namecheap plan
  * CDN [CloudFlare Dev mode](https://www.cloudflare.com/a/caching/worksatscale.com#development_mode) does a pass through for 3 hours
  * Stop use of CloudFlare while site is under development
  * Add DNS A record for www.worksatscale.com to point to `68.65.122.176`



 

-------------------------
##Starting XAMPP Services 
* allows functions on `localsite`
* `cd /opt/lampp/`
* `sudo ./manager-linux-x64.run`
 
-------------------------
##Plugs-ins
* General
  * Jetpack
* SEO
  * All in One SEO Pack
  * SEO Friendly Images
  * Google XML Sitemaps
* Cache
  * W3 Total Cache
* Security
  * iThemes Security
* Backup
  * UpdraftPlus Backup and Restoration
* Anti-Spam
  * Wordpress Zero Spam
  * Stop Spammers Spam Prevention
* Contact Form (Use Jetpack)
* Favicon
  * Favicon by RealFaviconGenerator (instead of Captain Favicon)

-------------------------
##References
* [Building Websites with Wordpress)(https://www.safaribooksonline.com/library/view/building-websites-with/9781771373265/)
* [Namecheap cPanel Login](https://server118.web-hosting.com:2083/)

