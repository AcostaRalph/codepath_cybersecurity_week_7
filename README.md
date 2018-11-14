# Project 7 - WordPress Pentesting

Time spent: **6** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** (3 required, 2 optional) affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID: User Enumeration
  - [x] Summary: 
    - Vulnerability types: User Enumeration
    - Tested in version: 4.2
    - Fixed in version: N/A
  - [x] GIF Walkthrough: <img src="https://github.com/AcostaRalph/codepath_cybersecurity_week_7/blob/master/user_enumeration.gif" width="800">
  - [x] Steps to recreate:
  	- Establish confirmation of connection to application using ```ping <url/ipaddress>```
  	- Run WPScan on application with enumeration option and user enumeration option using ```wpscan --url <url> -e u```
  	- Results, if successful should output near the end of the process
  - [x] Affected source code:
    - [Link 1](https://www.wpwhitesecurity.com/wordpress-username-disclosure-vulnerability/)
2. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS))
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [x] GIF Walkthrough: <img src="https://github.com/AcostaRalph/codepath_cybersecurity_week_7/blob/master/authenticated_stored_xss.gif" width="800">
  - [x] Steps to recreate: 
  	- As a user with author level access, one must edit/create a new post/page.
  	- Enter this code as an example ```<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>```
  	- This code can be hidden with a style tag to be transparent to hide malicious code which would execute on a mouseover of the link.
  - [x] Affected source code:
    - [Link 1](https://wpvulndb.com/vulnerabilities/8111)
3. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: <img src="https://github.com/AcostaRalph/codepath_cybersecurity_week_7/blob/master/YouTube_embeded.gif" width="800">
  - [x] Steps to recreate: 
  	- As a user with author level access, create a new post.
  	- Find a YouTube video to embed and get the embeded source tag from the video.
  	- Enter this code in the post ```[embed src='https://www.youtube.com/embed/dQw4w9WgXcQ\x3csvg onload=alert(1)\x3e'][/embed]```
  	- This code exectues as soon as the post is opened, and may hide malicious code when the user accesses the post.
  		- This may be hidden with a style tag so the user would not be aware.
  - [x] Affected source code:
    - [Link 1](https://wpvulndb.com/vulnerabilities/8768)

## Assets

No additional assets

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [Peek](https://github.com/phw/peek).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [2018] [Ralph Acosta]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.