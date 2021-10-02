# Fix-404-Error-React
Fix 404 Error When Using React-Router-Dom &amp; Nginx

#Open the Nginx sites-available configuration file for your website (replace default with the filename for your website)

    sudo nano /etc/nginx/sites-available/default
    
#And change the location section to the following:

    location / {
	  try_files $uri /index.html;
    }
    
Everything else in the file can be kept the same.
Save and close the file when you are finished.

#Next, test to make sure that there are no syntax errors in any of your Nginx files:
    
    sudo nginx -t
    
#If no problems were found, restart Nginx to enable your changes:
    
    sudo systemctl restart nginx
