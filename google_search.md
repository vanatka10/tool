| Operator      | Explain                                                    | Example                                        |
|---------------|------------------------------------------------------------|------------------------------------------------|
| intitle:      | Search within the title of a webpage                       | intitle:admin                                  |
|               |                                                            | intitle:index.of inurl:hits                   |
|               |                                                            | intitle:index.of inurl:wp-content             |
|               |                                                            | intitle:index.of inurl:wp-content/uploads    |
| inurl:        | Search within the URL                                      | inurl:wp-content/uploads filetype:sql         |
|               |                                                            | inurl:.ssh intitle:index.of authorized_keys  |
| intext:       | Search within the text of a webpage (user-accessible part)| intext:”whitehat.vn″                         |
|               |                                                            | intext:”Tòa nhà Bkav, Khu đô thị mới Yên Hòa, Cầu Giấy, Hà Nội” inurl:ftp |
|               |                                                            | inurl:”server-status” intext:”Apache Server Status” |
| allintext:/<br>allinurl:/<br>allintitle: | These are more complex. Essentially, they work similarly to the ones above | allintext: “Please login to continue…” “ZTE Corporation. All rights reserved.” |
|               |                                                            | allintitle:Welcome to Windows XP Server Internet Services |
| filetype:     | Limit desired file types                                   | filetype: xls intext:email intext: password  |
| site:         | Limit search results to specific websites                  | filetype: xls site: whitehat.vn              |
|               |                                                            | intitle:”index.of” site:mit.edu               |
| info:         | Displays all information related to linked webpages, including cached versions | info:apple.com                               |
| cache:        | Retrieves all caches that Google has for specific pages   | cache:sitepoint.com/javascripts/             |
| -             | Includes other conditions                                  | inurl:citrix inurl:login.asp -site:citrix.com|
| "search-term" | Surrounds phrases with "", ensuring exact search           | inurl:”server-status” intext:”Apache Server Status” |
| *             | Similar to using it in the terminal, representing unknown words | a * saved is a * earned                     |
| +             | Often used to fix search results to a specific phrase      | “Machine gun” +uzi                           |
| .             | Represents any character in that position in the search term | inurl:.ssh intitle:index.of authorized_keys  |
