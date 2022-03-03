


> Written with [StackEdit](https://stackedit.io/).
# Lab: Username enumeration via response timing
[Link lab](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-response-timing)

Test với user và pass linh tinh. 
![enter image description here](https://scontent.fhan2-4.fna.fbcdn.net/v/t1.15752-9/275042879_336414208422707_4720161599556004723_n.png?_nc_cat=104&ccb=1-5&_nc_sid=ae9488&_nc_ohc=tZbNg1mktpwAX8zAjhO&tn=8jbY9FUJSjcjysGn&_nc_ht=scontent.fhan2-4.fna&oh=03_AVJlil6vaVBmJS5pmEALH3XaDhjEZJ2XTTuFFqGl2DV9pw&oe=62451A6A)
 
 Khi login thì sẽ tự chuyển tới Burp Suite
 ![enter image description here](https://scontent.fhan2-2.fna.fbcdn.net/v/t1.15752-9/273973575_330737772187995_642018520885268443_n.png?_nc_cat=110&ccb=1-5&_nc_sid=ae9488&_nc_ohc=6WKJ5gBNp1AAX8h2E9y&_nc_ht=scontent.fhan2-2.fna&oh=03_AVKKnGrMAGhpl38g6c2tVo7pBGDuJHYG5EQWEEHAkOvNPw&oe=62485E6B)
 Chuyển sang Repeater
 ![enter image description here](https://scontent.fhan2-1.fna.fbcdn.net/v/t1.15752-9/274004864_261700026133648_5046497643565638742_n.png?_nc_cat=101&ccb=1-5&_nc_sid=ae9488&_nc_ohc=k7m-gUWjYLgAX8wEAuv&_nc_ht=scontent.fhan2-1.fna&oh=03_AVIYOsBctQwCssmBd00k8HLF175FEUovH0n1dbwCvq1ukg&oe=62458EAA)
Thêm X-Forwarded-For để giả mạo IP, đăng nhập sai vô số lần.
Vì Labs này đăng nhập 3 lần sai sẽ chặn IP
Sau đó send Intruder
![enter image description here](https://scontent.fhan2-3.fna.fbcdn.net/v/t1.15752-9/273915837_667045157946292_5432603962524379753_n.png?_nc_cat=109&ccb=1-5&_nc_sid=ae9488&_nc_ohc=gH_nRtKKS5MAX8eHbmC&tn=8jbY9FUJSjcjysGn&_nc_ht=scontent.fhan2-3.fna&oh=03_AVK4nAvCl5U16pasJGAi5jMwyYUBTP5UfU-SFwOD5OIyEw&oe=62477089)
Mật khẩu càng dài thì thời gian trả về càng lâu
![enter image description here](https://scontent.xx.fbcdn.net/v/t1.15752-9/259323823_293976406169583_4914856246529864386_n.png?stp=dst-png_s552x414&_nc_cat=108&ccb=1-5&_nc_sid=aee45a&_nc_ohc=ZQqfwrUAy3cAX8ZWgvD&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&oh=03_AVJ5zZUbwn536nkqQmpWgDu-5q8eAec6QQYWdbPNZHVW5A&oe=62468499)
![enter image description here](https://scontent.xx.fbcdn.net/v/t1.15752-9/272723742_1280367225827238_9024661181351610417_n.png?stp=dst-png_p403x403&_nc_cat=107&ccb=1-5&_nc_sid=aee45a&_nc_ohc=jrroFLdIXy4AX9zf6FN&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&oh=03_AVKWh5fhGmkhuX4GH0mJ4EjL-4tF3gL25TARNrhsjO9geQ&oe=624750A8)
Set up như hình để quét tài khoản đúng
Sau đó start attack
Tìm user có thời gian trả về lâu nhất
![enter image description here](https://scontent.xx.fbcdn.net/v/t1.15752-9/274334912_707168673979967_6290914567959603696_n.png?stp=dst-png_p403x403&_nc_cat=103&ccb=1-5&_nc_sid=aee45a&_nc_ohc=qXEEDRMZ_LwAX95LoZ7&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&oh=03_AVKMV6vJITUfuhgFvJz0hNzUrtAqFxMW7Jq3TWaxdGXMJA&oe=62473496)
