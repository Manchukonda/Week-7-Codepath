# Week-7-Codepath-hm1089
# Project 7 - WordPress Pentesting

Time spent: 8 hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. Vulnerability Name or ID : User Enumeration with wpscan
  - [ ] Summary:  The error message shows up when we enter the non-existing username gives as username doesn't exist. The error message shows up when we enter the existing username and password as wrong or empty , the message validates the password is                     incorrect.So, wpscan can enumerate and give the usernames that are existing.
    - Vulnerability types: User Enumeration
    - Tested in version: 4.2.2
    - Fixed in version: 
  - [ ] GIF Walkthrough: <img src="https://github.com/Manchukonda/Week-7-Codepath/blob/master/UserEnumeration%20Vunerability.gif" width="800">
  - [ ] Steps to recreate: 
        Observe the login names with existing and non-existing login names and with the respective error messages.
        Run "wpscan --url [INSERT_YOUR WORDPRESS URL] --enumerate u" command and observe the login names that are existing.
        By that way we can enumerate the login names.
  - [ ] Affected source code:
    - [Reference] (https://www.wpwhitesecurity.com/wordpress-username-disclosure-vulnerability/)
    - [Github] (https://github.com/WordPress/WordPress/blob/4.2-branch/wp-login.php)
    
 2. Vulnerability Name or ID : Cross-site Scripting in TwentyFifteen theme in edit post
    - [ ] Summary: XSS vulnerability in the text editor box in writing/editing posts.  
    - Vulnerability types:  XSS
    - Tested in version: 4.2.2
    - Fixed in version: 
  - [ ] GIF Walkthrough: <img src="https://github.com/Manchukonda/Week-7-Codepath/blob/master/XSS_1.gif" width="800">
  - [ ] Steps to recreate: 
          Navigate to wordpress page, Create a post with the body as <script> alert('XSS') </script> in the text editor mode. You cant see anything in the visual mode. Save the post and view the post. 
          Once the post is loaded the pop up arrives showing XSS.
  - [ ] Affected source code:
     - [Link] (https://core.trac.wordpress.org/browser/branches/4.2/src/wp-includes/class-wp-editor.php?rev=33361)
    
3. Vulnerability Name or ID : Cross-site Scripting in TwentyFifteen theme in title of post
  - [ ] Summary: XSS vulnerability in the text editor box in title of the posts. 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 
  - [ ] GIF Walkthrough: <img src="https://github.com/Manchukonda/Week-7-Codepath/blob/master/XSS_2.gif" width="800">
  - [ ] Steps to recreate: 
          Navigate to wordpress page, Create a post with the title as Image error load 
          <img src="hello" onerror=alert('XSS')>Hello</img> .
          Save the post and view the post. Once the post is loaded the pop up arrives showing XSS.
  - [ ] Affected source code:
    - [Link] (https://core.trac.wordpress.org/browser/branches/4.2/src/wp-includes/class-wp-editor.php?rev=33361)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).


## License

    Copyright [2018] [Harish Kumar Manchukonda]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
