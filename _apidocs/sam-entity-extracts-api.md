---
title: SAM.gov Entity/Exclusions Extracts Download APIs
banner-heading: SAM.gov Entity/Exclusions Extracts Download APIs
---


## Overview
The Extracts Download API permits SAM.gov users with valid roles to download entity and exclusions data extracts.<br>

The Entity Management extracts contain entities (businesses and government agencies) data from SAM.gov.  The Exclusions extract contains a list of all parties with a currently active exclusion in SAM.

  
1. **Entity Management Public Data Package:**
   * This extract contains entity registration data publicly available under the Freedom of Information Act (FOIA) for those registered in SAM.gov to do business with the Federal government.
   * All entities and data elements are classified as public.
   * End user needs to create an account in SAM.gov and procure an API_KEY to access these extracts.
   * File naming convention:<br />
	 Monthly ASCII (Default): SAM_PUBLIC_MONTHLY_YYYYMMDD.ZIP<br />
	 Monthly UTF-8 (Default): SAM_PUBLIC_UTF-8_MONTHLY_YYYYMMDD.ZIP<br />

2. **Entity Management Extracts FOUO (For Official Use Only) Data Package:**
   * This extract contains the same information as the Entity Management Public Data Package, plus data elements which are classified as For Official Use Only (FOUO).
   * The monthly extract is published on the first Sunday of the month and contains all active registrations plus registrations with an expiration date within the past 6 months.
   * The daily extract is an incremental file which is published 5 days a week (Tuesday – Saturday) and contains all new, updated, and deactivated registrations since the previous daily file.
   * End user needs to create a system account with FOUO access roles and procure an API_KEY to access these extracts.
   * Only system account keys can be used to access FOUO data.
   * Daily ASCII (Default): SAM_FOUO_DAILY_YYYYMMDD.ZIP<br />
	 Daily UTF-8: SAM_FOUO_UTF-8_DAILY_YYYYMMDD.ZIP<br />
	 Monthly ASCII (Default): SAM_FOUO_MONTHLY_YYYYMMDD.ZIP<br />
	 Monthly UTF-8 (Default): SAM_FOUO_UTF-8_MONTHLY_YYYYMMDD.ZIP<br />

3. **Entity Management Extract Sensitive Data Package:**
   * This extract contains the same information as the Entity Management FOUO Data package with the addition of data elements which are classified as Sensitive.
   * The monthly extract is published on the first Sunday of the month and contains all active registrations plus registrations with an expiration date within the past 6 months.
   * The daily extract is an incremental file which is published 5 days a week (Tuesday – Saturday) and contains all new, updated, and deactivated registrations since the previous daily file.
   * End user needs to create a system account with sensitive access roles and procure an API_KEY to access these extracts.
   * Only system account keys can be used to access Sensitive data.
   * Daily ASCII (Default): SAM_SENSITIVE_DAILY_V2_YYYYMMDD.ZIP<br />
     Daily UTF-8: SAM_SENSITIVE_UTF-8_DAILY_V2_YYYYMMDD.ZIP<br />
     Monthly ASCII (Default): SAM_SENSITIVE_MONTHLY_V2_YYYYMMDD.ZIP<br />
     Monthly UTF-8 (Default): SAM_SENSITIVE_UTF-8_MONTHLY_V2_YYYYMMDD.ZIP<br />
   * This extract requires IP address whitelisting to download your file.  You will need to keep an up-to-date list of your IP addresses in your System Account.


4. **Exclusions Public Data Package:**
   * This extract all active exclusions in SAM as a comma-separated value (CSV) file.
   * The Exclusions extract is a daily file, published 7 days per week.
   * End user needs to create an account in SAM.gov and procure an API_KEY to access these extracts.
   * File Name: SAM_Exclusions_Public_Extract_YYDDD.ZIP (Julian Date)<br />
   		* April 16, 2019 is the 106th day of 2019.  Therefore, the Exclusions extract for April 16, 2019 would be SAM_Exclusions_Public_Extract_19106.ZIP.

**Entity Extract Calendar**
<table>
<tr>
<td>Monthly Files for Public, FOUO and Sensitive Extracts</td>
<td>
* They are produced on the first Sunday of each month. Kindly check after 7 AM.<br/>
* The date on the .ZIP file matches the date when the file was generated. E.g.: The March monthly files were generated and dated on 20210307.<br/>
* The date on the .ZIP file matches the date on the .dat file inside.<br/>
* These files contain all active entities + entities expired in the last 6 months.
</td>
</tr>
<tr>
<td>Daily Files for FOUO and Sensitive Extracts</td>
<td>
* They are produced every Tuesday-Saturday. Kindly check after 7 AM.<br/>
* The date on the .ZIP matches the date when the file was generated. E.g: The file generated on the last Saturday of March will show 20210327.<br/>
* The date on the .ZIP file matches the date on the .dat file inside.<br/>
* These are incremental files that contain new/updated/deactivated/expired entities since the previous day’s file.
</td>
</tr>
</table>

<p><small><a href="#">Back to top</a></small></p>

## Getting Started

The Public and FOUO Entity extracts and Exclusion extracts are available using the following endpoints:
 
  * Production: https://api.sam.gov/data-services/v1/extracts?api_key= < value >
  * Alpha: https://api-alpha.sam.gov/data-services/v1/extracts?api_key= < value ><br><br>
  
  <div style="padding: 15px; border: 1px solid transparent; border-color: transparent; margin-bottom: 20px; border-radius: 4px; color: #31708f; background-color: #d9edf7; border-color: #bce8f1;">
       The Sensitive version of the extracts are no longer available via GET requests.
       Please refer to the “Sensitive Download API Process” to learn more about the Sensitive extract retrieval process.
       <ul>
        <li style="color: #31708f;">Production: https://api.sam.gov/data-services/v1/extracts?fileName=< name of the file ></li>
        <li style="color: #31708f;">Alpha: https://api-alpha.sam.gov/data-services/v1/extracts?fileName=< name of the file ></li>
        </ul><br>
  </div>  
     
Generating a personal API Key:
* Registered users can request for a public API on ‘Account Details’ page. This page can be accessed here: Account Details page on SAM.gov
* Users must enter their password on ‘Account Details’ page to view the API Key information. If an incorrect password is entered, an error will be returned.
* After the API Key is generated on ‘Account Details’ page, the API Key can be viewed on the Account Details page immediately. The API Key is visible until users navigate to a different page.
* If an error is encountered during the API Key generation/retrieval, then users will receive an error message and they can try again.

Generating a System Account API Key:
* Users registered with a non-government email address and associated with an entity OR users registered with a government email address may request a system account for public data access.
* If a user satisfies the above registration criteria they will be able to access the System Accounts widget from their Workspace page after logging in.
* The user can then select ‘Go to System Accounts’ from the widget and fill out the required sections.
* The requested system account will then need to be approved. After approval the user will be notified via email and they can also see the updated status in the System Account widget.
* The user can select ‘Go to System Accounts’ again in the widget from their workspace and enter a new system account password.
* After setting up the password the user will see a new section for retrieving a system account API Key.
* The user must enter their password again to retrieve the key.
* The user must maintain accurate IP addresses in their System Accounts, particularly if they are downloading the Entity Management Sensitive Data Package.

Type of Connections and Rate Limits
<table>
<tr>
<th style="background-color: #f1f1f1;"><b>Connecting Source</b></th>
<th style="background-color: #f1f1f1;"><b>Type of Connection</b></th>
<th style="background-color: #f1f1f1;"><b>Default Rate Limit</b></th>
</tr>
<tr>
<td>Non-federal user with no role</td>
<td>Personal API key</td>
<td>10 requests/day</td>
</tr>
<tr>
<td>Non-federal user with a role</td>
<td>Personal API key</td>
<td>1,000 requests/day</td>
</tr>
<tr>
<td>Federal User</td>
<td>Personal API key</td>
<td>1,000 requests/day</td>
</tr>
<tr>
<td>Non-federal system</td>
<td>System account API key</td>
<td>1,000 requests/day</td>
</tr>
<tr>
<td>Federal system</td>
<td>System account API key</td>
<td>10,000 requests/day</td>
</tr>
</table>


<p><small><a href="#">Back to top</a></small></p>

## API Description

### Extracts Download API Parameters

<b>Entity Management Extract Query String Parameters.</b>
<table>
<tr>
<th style="background-color: #f1f1f1;"><b>Parameter Name</b></th>
<th style="background-color: #f1f1f1;"><b>Description</b></th>
</tr>
<tr>
<td>api_key</td>
<td>Required element to identify API users and validate role-based access<br />
</td>
</tr>
<tr>
<td>fileName</td>
<td>Allows users to provide extract file name<br />
The fileName parameter must be used if the sensitivity parameter is not used.<br />
Example: fileName=SAM_PUBLIC_MONTHLY_20190323.ZIP
</td>
</tr>
<tr>
<td>fileType</td>
<td>Allows users to specify the domain of the extract that they wish to download<br />
The filetype parameter must be used if fileName is not specified.<br />
Permitted values: ENTITY, EXCLUSION, SCR, BIO<br />
</td>
</tr>
<tr>
<td>sensitivity</td>
<td>Allows users to provide the desired sensitivity level of the extract that they wish to download, if they have proper roles<br />
The sensitivity parameter must be used if fileName parameter is not used.<br />
Default value: PUBLIC<br />
Permitted values: PUBLIC, FOUO, SENSITIVE
</td>
</tr>
<tr>
<td>frequency</td>
<td>Allows users to request either a DAILY or MONTHLY extract<br />
Default value: MONTHLY<br />
Permitted values: DAILY, MONTHLY
</td>
</tr>
<tr>
<td>charset</td>
<td>Allows users to request either the ASCII or UTF-8 extract character-set<br />
Default value: ASCII<br />
Permitted values: ASCII, UTF8, UTF-8<br />
Note: This parameter is not applicable for the EXCLUSION file type.
</td>
</tr>
<tr>
<td>date</td>
<td>Allows users to select a specific date of the file that they wish to download.<br />
Format: MM/DD/YYYY for a specific date of  MM/YYYY to specify a year and month (for MONTHLY files only)<br />
Default value: Most recent date, depending on fileType<br />
Examples: 04/19/2019; 11/15/2018; 03/2019
</td>
</tr>
<tr>
<td>version</td>
<td>Allows users to select the file they wish to download by version.<br />
Default value: Most recent version, depending on fileType and/or sensitivity<br />
Examples: V1; V2; V3
</td>
</tr>
</table>

### Sensitive Download API Process

* All requests must be sent as POST calls using clients like Postman. These requests cannot be sent through browsers.
* The System Account User ID and Password must be sent as "Basic Auth" under the "Authorization" Header. The combination needs to be base 64 encoded as base64(username:password).
* The Sensitive api_key parameter with its value must be sent in the "Headers" as "x-api-key" and not directly in the request URL.
* "Accept" parameter must be passed in "Headers" with value, "application/zip".
* "Content-Type" parameter must be passed in "Headers" with value, "application/json".
* All the optional search filters can be sent in the request URL or in the "Body".

### Explanation of the API using Examples

The api_key parameter is required for identification and role-based access control.  After the api_key, there are query paths to download the correct file:<br>

Option 1: Using the fileName only.  The fileName is an exact match parameter which can be used for any type of file.  If you use the fileName parameter, no other parameters are required and will be ignored if included.<br>

Option 2: Using fileType and other parameters.  If you choose not to use the fileName, you may specify the fileType along with other parameters to identify which extract you wish to download.<br>

**Please refer to the SAM Master Extract Data List:**
<br>This spreadsheet contains a listing of data elements you may see in the extracts. Please refer to each data package's layout mapping file for further details.
<br><br>Before April 2022: <a href="v1/SAM_MASTER_EXTRACT_DATA_LIST.xlsx">SAM Master Extract Data List</a><br>
Effective April 2022: <a href="v1/SAM_MASTER_EXTRACT_DATA_LIST v6.0.xlsx">SAM Master Extract Data List</a>

**Entity Management Public Data Package Sample API calls:**<br>

Monthly File, Version 1, April 2019 (fileName):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileName=SAM_PUBLIC_MONTHLY_20190407.ZIP<br>

Monthly File, Version 1, April 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileType=ENTITY&sensitivity=PUBLIC&frequency=MONTHLY&date=04/2019&version=V1<br>

Monthly File (UTF-8), Version 1, April 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileType=ENTITY&sensitivity=PUBLIC&frequency=MONTHLY&date=04/2019&charset=UTF8&version=V1<br>

**Expected Result:**<br>
Click to view the full details of the data elements (pre-UEI): <a target="_blank" rel="noopener noreferrer" href="v1/public_extract_layout.pdf">Public Extract Layout</a><br>
Click to view the full details of the revised extract layout for the UEI/EVS changes (current until April 2022):<a target="_blank" rel="noopener noreferrer" href="v1/SAM_Entity_Management_Public_V2_Extract_Layout.pdf">Public Extract Layout</a><br>
Click to view the full details of the revised extract layout for the upcoming April 2022 release: <a target="_blank" rel="noopener noreferrer" href="v1/SAM Master Extract Mapping v6.0 Public File V2 Layout.xlsx">Public Extract Layout</a><br>

**Entity Management FOUO Data Package Sample API calls:**<br>

Daily File, Version 1, April 20, 2019 (fileName):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileName=SAM_FOUO_DAILY_20190420.ZIP<br>

Daily File, Version 1, April 20, 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileType=ENTITY&sensitivity=FOUO&frequency=DAILY&date=04/20/2019&version=V1<br>

Daily File (UTF-8), Version 1, April 20, 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileType=ENTITY&sensitivity=FOUO&frequency=DAILY&date=04/20/2019&charset=UTF8&version=V1<br>

Monthly File, Version 1, April 2019 (fileName):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileName=SAM_PUBLIC_MONTHLY_20190407.ZIP<br>

Monthly File, Version 1, April 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileType=ENTITY&sensitivity=FOUO&frequency=MONTHLY&date=04/2019&version=V1<br>

Monthly File (UTF-8),Version 1, April 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileType=ENTITY&sensitivity=FOUO&frequency=MONTHLY&date=04/2019&charset=UTF8&version=V1<br>

**Expected Result**<br>
Click to view the full details of the data elements (pre-UEI): <a target="_blank" rel="noopener noreferrer" href="v1/fouo_extract_layout.pdf">FOUO Extract Layout</a><br>
Click to view the full details of the revised extract layout for the UEI/EVS changes (current until April 2022):<a target="_blank" rel="noopener noreferrer" href="v1/SAM_Entity_Management_FOUO_V2_Extract_Layout.pdf">FOUO Extract Layout</a><br>
Click to view the full details of the revised extract layout for the upcoming April 2022 release: <a target="_blank" rel="noopener noreferrer" href="v1/SAM Master Extract Mapping v6.0 FOUO File V2 Layout.xlsx">FOUO Extract Layout</a><br>

**Entity Management Sensitive Data Package Sample API calls:**<br>

Daily File, Version 2, April 20, 2019 (fileName):<br>
https://api.sam.gov/data-services/v1/extracts?fileName=SAM_SENSITIVE_DAILY_V2_20190420.ZIP<br>

Daily File, Version 2, April 20, 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?fileType=ENTITY&sensitivity=SENSITIVE&frequency=DAILY&date=04/20/2019&version=V2<br>

Daily File (UTF-8), Version 2, April 20, 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?fileType=ENTITY&sensitivity=SENSITIVE&frequency=DAILY&date=04/20/2019&charset=UTF8&version=V2<br>

Monthly File, Version 2, April 2019 (fileName): <br>
https://api.sam.gov/data-services/v1/extracts?fileName=SAM_SENSITIVE_MONTHLY_V2_20190407.ZIP<br>

Monthly File, Version 2, April 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?fileType=ENTITY&sensitivity=SENSITIVE&frequency=MONTHLY&date=04/2019&version=V2<br>

Monthly File (UTF-8), Version 2, April 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?fileType=ENTITY&sensitivity=SENSITIVE&frequency=MONTHLY&date=04/2019&charset=UTF8&version=V2<br>

**Expected Result**<br>
Click to view the full details of the data elements (pre-UEI): <a target="_blank" rel="noopener noreferrer" href="v1/SAM Master Extract Mapping v5.6 Sensitive File V2 Layout.xlsx">Sensitive Extract Layout</a><br>
Click to view the full details of the revised extract layout for the UEI/EVS changes (current until April 2022): <a target="_blank" rel="noopener noreferrer" href="v1/SAM_Entity_Management_SENSITIVE_V3_Extract_Layout.xlsx">Sensitive Extract Layout</a><br>
Click to view the full details of the revised extract layout for the upcoming April 2022 release: <a target="_blank" rel="noopener noreferrer" href="v1/SAM Master Extract Mapping v6.0 Sensitive File V3 Layout.xlsx">Sensitive Extract Layout</a><br>

**Exclusions Public Data Package Sample API calls:**<br>

Daily File, Version 1, April 16, 2019 (fileName):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileName=SAM_Exclusions_Public_Extract_19106.ZIP<br>

Daily File, Version 1, April 16, 2019 (parameter):<br>
https://api.sam.gov/data-services/v1/extracts?api_key={API_KEY}&fileType=EXCLUSION&date=04/16/2019&version=V1<br>

**Expected Result**:
Click to view the full details of the data elements (pre-UEI): <a target="_blank" rel="noopener noreferrer" href="v1/SAM_Exclusions_Public_Extract_Layout.pdf">Exclusions Extract Layout</a><br>
Click to view the full details of the revised extract layout for the UEI/EVS changes (current until April 2022):<a target="_blank" rel="noopener noreferrer" href="v1/SAM_Exclusions_Public_V2_Extract_Layout.pdf">Exclusions Extract Layout</a><br>
Click to view the full details of the revised extract layout for the upcoming April 2022 release: <a target="_blank" rel="noopener noreferrer" href="v1/SAM_Exclusions_Public_Extract_Layout_V2_1.pdf">Exclusions Extract Layout</a><br>

**An example of the Sensitive extract download POST call using Postman:**<br>
Request URL:
https://api.sam.gov/data-services/v1/extracts?fileName=< name of the file ><br>
Click to view Sample Authorization <a target="_blank" rel="noopener noreferrer" href="v1/DOWNLOAD_API_AUTH.JPG">Sample Extract Authorization</a><br>
Click to view Sample Request Header <a target="_blank" rel="noopener noreferrer" href="v1/api_key.JPG">Sample Request Header</a>

<div style="font-family:Source sans pro; color: #212121; line-height: 1.5;">
<b>An example of the Sensitive extract download POST call using curl:</b><br>
Curl request with basic auth token: curl -X POST "https://api.sam.gov/data-services/v1/extracts?fileName=< fileName >" --header "X-Api-Key: < a valid API Key >" --header "Content-Type: application/json" --header "Accept: application/zip" --header "Authorization: Basic < auth token >" --output C:\sample_file.ZIP<br><br>
Curl request with username and password: curl -X POST "https://api.sam.gov/data-services/v1/extracts?fileName=< fileName >" --header "X-Api-Key: < a valid API Key >" --header "Content-Type: application/json" --header "Accept: application/zip" --user "< username >:< password >" --output C:\sample_file.ZIP</div>

**Sample File Names:**<br>

<b>The below sample files are for Alpha. Production has files from January 2020 onward.</b>

* FOUO files: 
  <br> SAM_FOUO_DAILY_20190423.ZIP<br>  SAM_FOUO_DAILY_20190522.ZIP<br>  SAM_FOUO_DAILY_20190523.ZIP<br>  SAM_FOUO_DAILY_20190524.ZIP<br>  SAM_FOUO_DAILY_20190525.ZIP<br> 
  SAM_FOUO_DAILY_20190528.ZIP<br>  SAM_FOUO_DAILY_20190529.ZIP<br>  SAM_FOUO_DAILY_20190530.ZIP<br>  SAM_FOUO_DAILY_20190531.ZIP<br>  SAM_FOUO_MONTHLY_20190430.ZIP<br> 
  SAM_FOUO_MONTHLY_20190505.ZIP<br>  SAM_FOUO_UTF-8_DAILY_20210204.ZIP<br>  SAM_FOUO_UTF-8_MONTHLY_20210204.ZIP<br> SAM_FOUO_DAILY_V2_20200824.ZIP<br>  SAM_FOUO_MONTHLY_V2_20200826.ZIP<br>  SAM_FOUO_UTF-8_DAILY_V2_20200824.ZIP<br>  SAM_FOUO_UTF-8_MONTHLY_V2_20200826.ZIP

* Sensitive files:
  <br> SAM_SENSITIVE_UTF-8_DAILY_V2_20190530.ZIP<br>  SAM_SENSITIVE_UTF-8_DAILY_V2_20190531.ZIP<br>  SAM_SENSITIVE_UTF-8_DAILY_V2_20190601.ZIP<br> 
  SAM_SENSITIVE_UTF-8_DAILY_V2_20190523.ZIP<br>  SAM_SENSITIVE_UTF-8_DAILY_V2_20190524.ZIP<br>  SAM_SENSITIVE_UTF-8_DAILY_V2_20190525.ZIP<br> 
  SAM_SENSITIVE_UTF-8_DAILY_V2_20190528.ZIP<br>  SAM_SENSITIVE_UTF-8_DAILY_V2_20190529.ZIP<br>  SAM_SENSITIVE_UTF-8_DAILY_V2_20190522.ZIP<br> 
  SAM_SENSITIVE_DAILY_V2_20190606.ZIP<br>  SAM_SENSITIVE_MONTHLY_V2_20190602.ZIP<br>  SAM_SENSITIVE_DAILY_V2_20190525.ZIP<br> 
  SAM_SENSITIVE_DAILY_V2_20190528.ZIP<br>  SAM_SENSITIVE_DAILY_V2_20190529.ZIP<br>  SAM_SENSITIVE_DAILY_V2_20190530.ZIP<br> 
  SAM_SENSITIVE_DAILY_V2_20190531.ZIP<br>  SAM_SENSITIVE_DAILY_V2_20190601.ZIP<br>  SAM_SENSITIVE_DAILY_V2_20190604.ZIP<br> 
  SAM_SENSITIVE_DAILY_V2_20190605.ZIP<br>  SAM_SENSITIVE_DAILY_V2_20190524.ZIP<br>  SAM_SENSITIVE_UTF-8_DAILY_V2_20190604.ZIP<br>  SAM_SENSITIVE_DAILY_V2_20190523.ZIP<br> 
  SAM_SENSITIVE_MONTHLY_V2_20200826.ZIP<br> SAM_SENSITIVE_DAILY_V2_20200827<br> SAM_SENSITIVE_DAILY_V3_20200827.ZIP<br>  SAM_SENSITIVE_MONTHLY_V3_20200826.ZIP<br> SAM_SENSITIVE_UTF-8_DAILY_V3_20200827.ZIP<br>  SAM_SENSITIVE_UTF-8_MONTHLY_V3_20200826.ZIP
  
* Public files:
  <br> SAM_PUBLIC_UTF-8_MONTHLY_V2_20200826.ZIP<br>  SAM_PUBLIC_MONTHLY_V2_20200826.ZIP<br> SAM_PUBLIC_UTF-8_MONTHLY_V2_20210103.ZIP<br> SAM_PUBLIC_MONTHLY_V2_20210103.ZIP<br> 
  SAM_PUBLIC_MONTHLY_20210103.ZIP<br> SAM_PUBLIC_UTF-8_MONTHLY_20210103.ZIP<br> SAM_PUBLIC_MONTHLY_20190407.ZIP<br>

## OpenAPI Specification File 

You can view the full details of this API's in the OpenAPI Specification file available here:<br>
<a href="v1/openapi.yaml">Open API specification file for the Entity/Exclusions Extracts Download API</a>

<p><small><a href="#">Back to top</a></small></p>

## Sample Extract Files
 
1. Existing Extract files:
* Click to view <a href="v1/sample-files/SAM_PUBLIC_MONTHLY_20140504.ZIP">Public Monthly V1 Extract File</a>
* Click to view <a href="v1/sample-files/SAM_FOUO_MONTHLY_V1_20140504.ZIP">FOUO Monthly V1 Extract File</a>
* Click to view <a href="v1/sample-files/SAM_SENSITIVE_MONTHLY_V2_20170702.ZIP">Sensitive Monthly V2 Extract File</a><br><br>

2. Updated Version of Extract files with UEI Information:
* Click to view <a href="v1/sample-files/SAM_PUBLIC_MONTHLY_V2_20200414.ZIP">Public Monthly V2 Extract File</a>
* Click to view <a href="v1/sample-files/SAM_FOUO_MONTHLY_V2_20200414.ZIP">FOUO Monthly V2 Extract File</a>
* Click to view <a href="v1/sample-files/SAM_SENSITIVE_MONTHLY_V3_20200414.ZIP">Sensitive Monthly V3 Extract File</a>
* Click to view <a href="v1/sample-files/SAM_Exclusions_Public_Extract_V2_22018.zip">Exclusions Public V2 Extract File</a><br>

<p><small><a href="#">Back to top</a></small></p>

## HTTP Response Codes

The API will return one of the following responses:

| HTTP Response Code | Description |
| ---- | ----------- |
| 200 | Successful. Data will be returned in JSON format. |
| 400 | Application Level Error Messages: <br>* User does not have permission to download the file. <br />* Missing required parameters, fileName OR fileType<br />* The requested extract file not found<br />* Invalid date format<br />* This http method is not allowed to download sensitive extracts. Only POST is supported for sensitive extracts.<br />* This http method is not allowed to download non-sensitive extracts. Only GET is supported for non-sensitive extracts.<br />* No api_key was supplied in request body. Please submit with a valid API key.<br />* No system account credentials are provided. Please provide credentials via basic authentication.<br>* The parameter fileName cannot be used with any other parameters.<br>* The File does not exist with the provided parameters<br>* The requested extract file needs FOUO roles to download<br>* IP Addresses associated with this System Account are different from that sending the request. Please submit your requests from a valid system.<br>* Insufficient privileges to perform the operation - System account must have Type of Connection as Restful.
| 406 | Invalid Accept Header. |
| 415 | Invalid Content-Type Header. |

<p><small><a href="#">Back to top</a></small></p>

## Contact Us

* Reach out to the SAM.gov team at <a href="https://www.fsd.gov" target="_blank">www.fsd.gov</a> for inquiries and help desk support.
    * Before contacting the help desk, conduct your own initial troubleshooting
        * Conduct a recent review of the open.gsa.gov/api specifications
        * Confirm you are using an API tool, not a browser to send the request. (FOUO & Sensitive Calls)
        * Confirm you are using the username/password for the system account that created the API key in the authentication header. (Sensitive Calls)
        * Confirm you used POST and not GET for this request (Sensitive Calls)
        * Confirm that the API key is from a system account (FOUO & Sensitive Calls)
        * Confirm that the API key being used is still active
        * Confirm that the system account you are using has “read fouo” or “read sensitive” permissions as applicable (FOUO & Sensitive Calls)
        * <b>Confirm that the IP addresses registered with your system account are current</b>
    * When submitting help desk tickets for API or system connection issues, provide the following:
        * The exact API requests that you were trying to send
        * The exact error messages that you were receiving
        * The exact dates and times when you received the errors
        * Screenshots (with the actual API request and the error)  [Attach to the ticket]
        * The System Account ID/Name that was trying to make API calls
        * Screenshots of the parameters used for API call   [Attach to the ticket]
        * Screenshots of the Headers used for the API call   [Attach to the ticket]
* Users requesting access to the test site (alpha.sam.gov) should follow the below steps.  These steps ONLY apply to alpha.sam.gov access requests.
    1. Navigate to <a href="https://www.fsd.gov" target="_blank">www.fsd.gov</a>
    2. Sign into the FSD platform using your FSD credentials
    3. Select "Create an Incident"
    4. Create an Incident
        <ol type="a">
        <li><b>System Name:</b> System for Award Management (SAM)</li>
        <li><b>Is this related to the American Rescue Plan Act?:</b> No</li>
        <li><b>Issue Type:</b> Other</li>
        <li><b>Business Type:</b> Other</li>
        <li><b>Subject (select 1):</b>
           <ol type="i">
           <li><b>Option A:</b> I need a role to test in alpha.sam.gov.</li>
           <li><b>Option B:</b> System account approval in alpha.sam.gov</li>
           </ol>
        </li>
        <li><b>Please describe the issue:</b> (Copy and paste the below information into the ticket, filling in your information within the brackets)
           <ol type="i">
           <li><b>Option A:</b> I have already navigated to alpha.sam.gov and created a user account, following the same steps for <a href="https://www.fsd.gov/gsafsd_sp?id=gsafsd_kb_articles&sys_id=81d067071b80b0109ac5ddb6bc4bcb63" target="_blank">creating an account</a> in sam.gov.  I would like to conduct testing but do not have the necessary role(s) in alpha.sam.gov.   The account that needs role assignment is associated with [EMAIL ADDRESS].  I request a [ROLE] role for the  [DOMAIN] domain in alpha.sam.gov.</li>
           <li><b>Option B:</b> I am creating/editing a system account and have submitted my account in alpha.sam.gov for approval.   I would like to request alpha.sam.gov system account review and approval for [Name of the alpha.sam.gov system account].</li>
           </ol>
        </li>
        </ol>

<p><small><a href="#">Back to top</a></small></p>

## Change Log

Date | Version | Description
------|---------------|---------
06/03/2019 | v1.0 | Base Version
08/15/2019 | v1.1 | * Added Beta.SAM.Gov to the page title. <br><br>* Clarified the Alpha and Beta endpoints.
12/20/2019 | v1.2 | * Added Sample FOUO and Sensitive File Names and Revised extract layouts for the upcoming UEI/EVS changes. <br><br> * Added "COMING SOON" section for upcoming changes to Alpha and Beta endpoints to meet new API standards.
02/25/2020 | v1.3 | * Updated Alpha endpoint to meet new API standards.<br><br> * Added Sample Extract Files.
02/28/2020 | v1.4 | * Updated Beta endpoint to meet new API standards.<br><br> * Removed "COMING SOON" information in Getting Started section. <br><br> * Added FOUO and Sensitive Sample Extract Files for different versions.
04/20/2020 | v1.5 |  Updated Public, FOUO and Sensitive Sample Extract Files that includes UEI information.
06/10/2020 | v1.6 |  Added the endpoint, new process and an example for the Download API .
08/17/2020 | v1.7 | * The Sensitive Alpha endpoint in "Getting Started" has been corrected and the Sample Extract Authorization screenshot in "Explanation of the API using Examples" has also been updated to reflect the correct endpoint.<br><br> * Sensitive data sample calls in the "Explanation of the API using Examples" have also been updated to show that the API key is no longer sent in the request URL.<br><br> * The "Sensitive Download API Process" section has been updated with additional steps for sending Sensitive requests (sending "Accept" and "Content-Type" parameters).<br><br> * The Sample Request Header screenshot in the "Explanation of the API using Examples" has been updated to reflect the new parameters as well. Two new codes (406, 415) have been added in the "HTTP Response Codes" section.
08/31/2020 | v1.8 | * Updated the Getting Started section to include the Sensitive Beta endpoint.
02/05/2021 | v1.9 | * Added V1/V2 Public, V3 Sensitive, and V2 FOUO files available in Alpha S3.<br><br>* Added version parameter<br><br>* Updated error messages<br><br>* Added note to charSet parameter stating exclusions file type is not applicable
03/12/2021 | v2.0 | * Added additional FOUO sample files.<br><br> * Added note that only system account keys can be used for FOUO and sensitive downloads.
04/08/2021 | v2.1 | * Updated Contact Us information.<br><br> * Added Entity Extract Calendar under Overview.
04/29/2021 | v2.2 | * Added note above list of sample files mentioning that files are for Alpha.<br><br>* Added description to 400 http response code describing Type of Connection error.<br><br>* Updated openapi spec file.
05/12/2021 | v2.3 | * Updated instances of beta.sam.gov to SAM.gov.<br><br> * Removed non-relevant information for Beta api.
07/16/2021 | v2.4 | * Updated the instructions on sending "Basic Auth" under the "Authorization" header.<br><br> * Added the Type of Connections and Rate Limits table.<br><br> * Updated the Contact Us information.<br><br> * Added example curl requests.
09/21/2021 | v2.5 | * Added the "Please refer to the SAM Master Extract Mapping document" subsection under the "Explanation of the API using Examples" section.
10/06/2021 | v2.6 | * Updated the "Contact Us" section. 
10/21/2021 | v2.7 | * Added Expected Results to Data Package Sample API Calls.<br><br> * Updated Extract Mapping Files.
02/01/2022 | v2.8 | * Updated the Exclusions Extract Layout file.<br><br> * Updated the Exclusions Public V2 Extract file.
03/11/2022 | v2.9 | * Added clarifying text for the April 2022 UEI transition.

<p><small><a href="#">Back to top</a></small></p>
