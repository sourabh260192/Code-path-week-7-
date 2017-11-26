# Project 7 - WordPress Pentesting
 
Time spent: More than 4 weeks 

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID - Authenticated Stored Cross-Site Scripting
  - [ ] Summary:  Cross-site scripting vulnerability in the text editor box in pages and writing/editing posts.
    - Vulnerability types:XSS
    - Tested in version:4.2.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: In post/page editor method, when logged in from contributor  ( post if accepted blindingly) and above, can type in "link" triggering XSS in text editor mode.
  - [ ] Affected source code:
    - https://klikki.fi/adv/wordpress3.html
	- https://core.trac.wordpress.org/browser/branches/4.2/src/wp-includes/class-wp-editor.php?rev=33361

1. (Required) Vulnerability Name or ID  - Password Brute Force Attack
  - [ ] Summary: Using rockyou.txt wordlist and wpscan, together with the user enumeration shown in number 2, the password of a particular username can be guessed by brute force because wordpress by default does not limit the number of login attempts.
    - Vulnerability types: Login Vulnerability
    - Tested in version: 4.2.2
    - Fixed in version:  4.7
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: Download the rockyou.txt dictionary file through apt-get install wordlists. Run "wpscan --url [INSERT_WORDPRESS_URL_NAME] --enumerate u" in kali linux (to enumerate users). Then, run "wpscan --url [INSERT_WORDPRESS_URL_NAME] --wordlist [PATH_TO_ROCKYOU_DICTIONARY - usually, it's /usr/share/wordlists/rockyou.txt" --username [USERNAME_YOU_FOUND_FROM_USER_ENUMERATION]" in kali linux.
  - [ ] Affected source code:
    - [Link 1]
1. (Required) Vulnerability Name or ID - User List Table Cross-Site Scripting (XSS)
  - [ ] Summary: 
    - Vulnerability types: XSS 2
    - Tested in version: 4.2
    - Fixed in version: 4.4.1.8
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate:   Make a comment with
     <p>TEST!!!<figure style="width: 1px;" class="wp-caption alignnone"><figcaption class="wp-caption-text">
     <a href="</figcaption></figure></a><a href="http://onMouseOver='alert(1)'">Click me</a></p>
  - [ ] Affected source code: https://blog.checkpoint.com/2015/09/15/finding-vulnerabilities-in-core-wordpress-a-bug-hunters-trilogy-part-iii-ultimatum/
    - [Link 1]
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types: Redirect to other target site
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Was not able to set up vagrant issues with virtualization hardware and hyper v , took weeks to get around it 

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
