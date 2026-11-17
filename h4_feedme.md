## x) Why use a feed reader (and RSS/Atom)?

- It solves a problem of not having to visit multiple webpages and wasting time skimming through headlines or personal preference data being collected, instead having a single document that lists recent items, each with a title, a link, a publication date, and some body content. A reader fetches the file on a schedule and shows the user new updates chronically.

- RSS either stands for RDF (Resource Description Framework) Site Summary or Really Simple Syndication https://www.britannica.com/technology/RSS.

- Atom and RSS are both web feed formats based on XML. If you need advanced features and customisation options, Atom might be the better choice. However, if you prioritize broad compatibility and simplicity, RSS could be the more suitable option https://thisvsthat.io/atom-vs-rss.

## y) Summary of Supreme court of Finland, [case Osuuspankkikeskus port scan KKO:2003:36](https://www.finlex.fi/fi/oikeuskaytanto/korkein-oikeus/ennakkopaatokset/2003/36)
- Port scanning can constitute attempted computer break-in when it is systematically used to find vulnerabilities with the intention of gaining unauthorised access, even if the firewall prevents actual entry.
- Port scanning itself can be legitimate for security testing, but the Supreme Court concluded that in this case the circumstances showed an intention to use the discovered information for unauthorized access.
- The defendant was also liable for the organization's investigation and cybersecurity-related costs, because these were considered foreseeable consequences of the attempted intrusion. His age (17) did not justify reducing the compensation given his technical experience and intentional conduct.

## a) Feed reader installation

<img width="1631" height="1031" alt="Screenshot 2026-11-16 at 22 06 02" src="https://github.com/user-attachments/assets/18da1156-41d2-4969-a7e9-fa686b171db8" />

## b) Add a feed for [Krebs](https://krebsonsecurity.com/feed/)

<img width="1631" height="1031" alt="Screenshot 2026-11-16 at 22 06 47" src="https://github.com/user-attachments/assets/1fc3c17a-ae22-4ce3-9f07-325177d2c11b" />

## c) Add a feed for Schneier on Security

<img width="1631" height="1031" alt="Screenshot 2026-11-16 at 22 08 27" src="https://github.com/user-attachments/assets/11b4a414-7bdf-4f8c-994a-dc8deab7e5f3" />

## d) Find and add two more security related feeds

Added HackerOne and Hacker Noon because I want to follow Hacker Noon to understand what is happening across tech and cybersecurity, and HackerOne to learn how vulnerabilities are actually discovered and handled in practice. How I found them was from long time ago by chatting with friends who were working in cybersec on how to keep up to date with the industry updates.

## e) Follow security feeds for a while

In general, I found a feed reader useful for keeping a broad awareness of the cybersecurity scene without repeatedly checking many websites. Its main weakness is that subscribing is easy, but deciding what is actually worth reading is still up to me. Information overload can become a problem and a feed reader requires more manual curation.

## f) Port scan
How can criminals know what services your employer has? Disconnect your computer from the internet while doing the test (after you have installed the required software). Do the test inside your virtual machine.
- Install nmap port scanner.
```ls
$ sudo apt-get update
$ sudo apt-get -y install nmap
``
- Disconnect from the internet. Show that 'ping 8.8.8.8' stops working when internet is disconnected.
  
  ```ls
$ ping 8.8.8.8
ping: connect: Network is unreachable
``
- Port scan your own computer. Use "localhost" as the address.
  
  ```ls
$ sudo nmap -A -v localhost
  ``
- Install a daemon.
  
```ls
$ sudo apt-get install apache2
$ sudo systemctl start apache2
``
- Port scan again.
  
 ```ls
$ sudo nmap -A -v localhost
``
- Analyze and explain the results.
TCP/IP fingerprint is different in each case.
  - localhost without another daemon:
    ```
    Host is up (0.000067s latency).

    Not shown: 999 closed tcp ports (reset)

    TCP Sequence Prediction: Difficulty=264 (Good luck!)

    Nmap done: 1 IP address (1 host up) scanned in 18.19 seconds
           Raw packets sent: 1110 (52.890KB) | Rcvd: 2211 (98.944KB)
    ``

  - with a daemon:
  ```
  Host is up (0.000070s latency).

  Not shown: 998 closed tcp ports (reset)
  
  80/tcp  open  http    Apache httpd 2.4.71 ((Debian))
  |_http-server-header: Apache/2.4.71 (Debian)
  |_http-title: Apache2 Debian Default Page: It works
  | http-methods: 
  |_  Supported Methods: GET POST OPTIONS HEAD
  
  Nmap done: 1 IP address (1 host up) scanned in 19.11 seconds
             Raw packets sent: 1110 (52.890KB) | Rcvd: 2212 (98.988KB)
  ``

  
- Do not scan random computers.

## g) Voluntary bonus
Identify a port scan against Apache on the host being scanned, e.g. in logs. Perform the test against "localhost" address and disconnect the internet while port scanning.
## h) Voluntary bonus
Modify nmap scan so that it cannot be detected by the method you found above.
