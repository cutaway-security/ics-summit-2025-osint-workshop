---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 5: Start SpiderFoot Information Gathering

### SpiderFoot Overview

Gathering OSINT information can be performed manually. While this is effective, there are many commercial and open source tools that provide automated OSINT gathering. Many of these tools use services that require the user create accounts to interact with the service's data collection capabilities. These methods are very effective but creating accounts with all of the different services can be time consuming and difficult to maintain over time. For the casual OSINT researcher or during quick vulnerability assessments using these automated tools without setting up accounts with services can be still be valuable. 

An OSINT tool that works well without setting up OSINT service accounts is the [SpiderFoot](https://github.com/smicallef/spiderfoot){:target="_blank"}. This tool is [one of the packages that can be installed in a Kali](https://www.kali.org/tools/spiderfoot/){:target="_blank"} system or virtual machine. The tool has a web-based interface that accepts IP address, domain names, and other details as targeting information. The tool can be configured to run a variety of over [200 modules](https://github.com/smicallef/spiderfoot#modules--integrations){:target="_blank"} to query online resources and the target's internet accessible service to collect information. These modules are extremely comprehensive and can follow paths, from data collected, that would be difficult to manually replicate. The output results are displayed to the user for manual analysis and can be used to generate different styles of reports.

### Preparing SpiderFoot

For this workshop we are going to be using SpiderFoot to conduct an automated review of the target, as selected in [Task 3](task3.md). The SpiderFoot tools is very flexible and can be configured to run comprehensive or less intense information gathering activities. To limit the impact on the identified target we will be using the tool's `Passive scan` technique.

The following examples will be examples of how to run the SpiderFoot tool in Kali. If the tool is not installed on your Kali VM you can follow the [Kali instructions for the installation](https://www.kali.org/tools/spiderfoot/){:target="_blank"}. Of course, you do not need to use Kali. If you have your own system with SpiderFoot installed, or you are [running SpiderFot using a Docker container](https://github.com/smicallef/spiderfoot/blob/master/Dockerfile){:target="_blank"}, the steps should be the same, or similar, on your preferred version. If you prefer, instructions for [installing in Microsoft Windows](#running-spiderfoot-on-windows) are included at the end of this task.

### Running SpiderFoot in Kali

1. Log into Kali and start a Terminal.

2. Run the following command to start the SpiderFoot web interface on the localhost on port 5000.

    `spiderfoot -l 127.0.0.1:5000`

3. Open the web browser and navigate to the following URL.

    `https://127.0.0.1:5000`

4. Once the tool is running, locate and click the `New Scan` tab in the main menu.

5. In the `Scan Name` text box type the name of the target organization and add the term "passive" at the end. For example `ACME - passive`. This will indicate the scan of the target is gathering information without connecting to the target organizations assets.

6. In the `Scan Target` textbox type the Fully Qualified Domain Name (FQDN) for the target. For example, `acme.com`.

7. Scroll down and select the radio button for the `Passive` scan. Note that this scan is used when "When you don't want the target to even suspect they are being investigated."

8. Click the `Run Scan Now` button. The web interface will change to provide a summary of the current state of the scan. 

9. Be patience. Even a passive scan can take up to twelve hours or more to complete.

10. If you need to stop the scan, change to the `Scans` tab in the main menu. Locate the scan by the scan name. Locate the `Stop Scan` button in the `Action` column. Clicking this button will stop the scan in a manner that it can be resumed at a later time. 

### Analyze the Results

This scan will be running long after the workshop ends. So, at this point, go ahead and move onto [Task 6](./task6.md). Periodically review this data as it is being collected. But do not wait for it to complete, it will definitely take a long time.

Before completing this workshop, do pause the scan. You can restart it when you have more time.

### Questions to Answer

1. How many subdomains does the organization have?
2. Are any of these subdomains for test servers or remote access?
3. Were any API endpoints identified?
4. Did you get a list of known email addresses?
5. Were any of these email addresses members of known, publicly exposed, data breaches?
6. How long did the scan take? Note: The `All` scan will take significantly longer.

### AI Analysis Query

Using an AI tool, run the following query to help identify areas of focus. These results should be used to help organize your thoughts and also remind you of some of the features you may have forgotten or did not know about. Adjust the query if it is not specific enough about SpiderFoot's capabilities or try one of the other AI tools.

> Considering the output of a SpiderFoot passive analysis, what are the key areas I should review when conducting an OSINT analysis of my company with the intent to understand potential disclosures and vulnerabilities?

## Next Step

When you are done, move onto [Task 6](task6.md): Domain Name Service Exploration.

## Additional Installation Directions

### Running SpiderFoot on Windows

SpiderFoot can be run on Microsoft Windows. The following steps require that Git, Python >= 3.7, and Pip are installed. Clone the SpiderFoot repository into a Tools or your Download directory. Change into the repository's directory and update the Python requirements. You can then run the SpiderFoot web interface and follow the `New Scan` directions starting at step four of the [Kali setup](#running-spiderfoot-in-kali).

Windows installation steps.

```ps1con
git clone https://github.com/smicallef/spiderfoot.git
cd .\spiderfoot\
pip3 install -r requirements.txt
python3 ./sf.py -l 127.0.0.1:5000
```