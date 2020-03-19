# Project 7 * 8 - WordPress Pentesting

## Pentesting Report

1. XSS 1: Comment Vulnerability
  - Summary: A payload can be injected as a comment on the main page, which will then exploit an XSS vulnerability upon publishing the comment.
  - Steps to recreate:
      1. Login as Admin
      2. Navigate to comments
      3. Post comment with the following payload:
      
<a href='/wp-admin/' title="XSS" style="position:absolute;top:0;left:0;width:100%;height:100%;display:block;" onmouseover=alert(1)//‘ rel="nofollow">Hello World</a>

  - Walkthrough:
  - Tested in version: 4.2
  - Fixed in version: 4.2.1
  
2. XSS 2: Edit Page Vulnerability
  - Summary: A script can be added to the end of the title of a page, which will then exploit an XSS vulnerability. The added script will not be visible in the published blog page, but will trigger an alert.
  - Steps to recreate:
      1. Login as Admin
      2. Navigate to All Pages
      3. Select a page to edit
      4. Add the following script to the page title and update: <script>alert(1)</script>

  - Walkthrough:
  - Tested in version: 4.2
  - Fixed in version: 4.7.1
  
3. XSS 3: Edit Post Vulnerability
  - Summary: A script can be added to the end of the title of a post, which will then exploit an XSS vulnerability upon reloading the main page.
  - Steps to recreate:
      1. Login as Admin
      2. Navigate to the Posts
      3. Select a post to edit
      4. Add the following script to the post title and update: <script>alert(1)</script>  
      5. Reload the main page
      
  - Walkthrough:
  - Tested in version: 4.2
  - Fixed in version: 4.2.5
  
4. XSS 4: Plugin Update Vulnerability 
  - Summary: A script can be added to the php of a chosen plugin, which will then exploit an XSS vulnerability upon loading the updates page within the dashboard tab. 
  - Steps to recreate:
      1. Login as Admin
      2. Navigate to Plugins
      3. Select a plugin to edit
      4. Add the following script script to the php and update: <script>alert(1)</script>  
      5. Navigate to Updates in the Dashboard

  - Walkthrough: 
  - Tested in version: 4.2
  - Fixed in version: 4.7.1
