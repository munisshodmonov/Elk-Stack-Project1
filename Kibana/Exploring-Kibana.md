## Activity File: Exploring Kibana

* You are a DevOps professional and have set up monitoring for one of your web servers. You are collecting all sorts of web log data and it is your job to review the data regularly to make sure everything is running smoothly. 

* Today, you notice something strange in the logs and you want to take a closer look.

* Your task: Explore the web server logs to see if there's anything unusual. Specifically, you will:

:warning: **Heads Up**: These sample logs are specific to the time you view them. As such, your answers will be different from the answers provided in the solution file. 

---

### Instructions

1. Add the sample web log data to Kibana.

2. Answer the following questions:

    - In the last 7 days, how many unique visitors were located in India?
       ![](Images/India-7-day.PNG)
    - In the last 24 hours, of the visitors from China, how many were using Mac OSX?
        ![](Images/China24-OSX.PNG)
    - In the last 2 days, what percentage of visitors received 404 errors? How about 503 errors?
      - 404 = 100%
      - 503 = 0%
    - In the last 7 days, what country produced the majority of the traffic on the website?
    - China with 20% of the traffic
    - Of the traffic that's coming from that country, what time of day had the highest amount of activity?
     - China at the 10 hour of the day
    - List all the types of downloaded files that have been identified for the last 7 days, along with a short description of each file type (use Google if you aren't sure about a particular file type).
       ![](Images/most-downloaded-files.PNG)
       - **gz - gzip uses compression archives that use compression algorithm**
       - **css - Cascading Style Sheets that is used to style and layout for web pages**
       - **zip - type of format that uses lossless data compression**
       - **deb - debian type of format for Debian Linux distribution**
       - **rpm - Red Hat Packet Manager**
3. Now that you have a feel for the data, Let's dive a bit deeper. Look at the chart that shows Unique Visitors Vs. Average Bytes.
     - Locate the time frame in the last 7 days with the most amount of bytes (activity).
     - 10,735
     - In your own words, is there anything that seems potentially strange about this activity?
     - 3 suspecious visitors.

4. Filter the data by this event.
     - What is the timestamp for this event?
     - Feb 6, 2022 @ 21:57:28.552, Feb 6, 2022 @ 23:08:08.182, Feb 6, 2022 @ 23:24:09.240
     - What kind of file was downloaded?
     - ZIP, APM and RPM
     - From what country did this activity originate?
     - US, China and India
     - What HTTP response codes were encountered by this visitor?
     - 200
5. Switch to the Kibana Discover page to see more details about this activity.
     - What is the source IP address of this activity?
     - 	35.143.166.159, 73.105.236.24, 223.112.248.233
     - What are the geo coordinates of this activity?
     -  "lat": 43.34121, "lon": -73.6103075, 2. "lat": 42.99821222, "lon": -74.32955111, 3. "lat": 37.85008167, "lon": -83.84575194
     - What OS was the source machine running?
     - Linux 
     - What is the full URL that was accessed?
     - https://artifacts.elastic.co/downloads/beats/metricbeat/metricbeat-6.3.2-i686.rpm, 	https://artifacts.elastic.co/downloads/kibana/kibana-6.3.2-windows-x86_64.zip, https://www.elastic.co/downloads/apm
     - From what website did the visitor's traffic originate?
     -  http://nytimes.com/warning/georgi-beregovoi, http://twitter.com/success/maksim-surayev, http://facebook.com/success/jay-c-buckey
6. Finish your investigation with a short overview of your insights. 

     - What do you think the user was doing?
     - All of them were downloading a file from elastic.
     - Was the file they downloaded malicious? If not, what is the file used for?
     - The files are not malicious they are used for a kibana setup
     - Is there anything that seems suspicious about this activity?
     - No, they were downloading from a legitimate source
     - Is any of the traffic you inspected potentially outside of compliance guidlines?
     - Everything looks normal there was nothing suspecious.

---
?? 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  
