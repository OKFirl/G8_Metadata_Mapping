####United States Metadata

**Where to Find Data**

The U.S. is currently implementing a new Open Data Policy, as outlined in the [Managing Information as an Asset](http:/project-open-data.github.io) memorandum. On November, 9, 2013 you can access all public federal government data at data.gov, and government data owned/maintained by specific federal agencies by going to *agency.gov*/data.json. Until then, much, but not all, public government data will be available at these locations, described using the metadata below.

**Metadata Details**

Concept|Description|Front-end (human-readable)|National metadata schema|Back-end machine-readable|Required|Data Type|Format: pattern|Cardinality|Usage Notes
------- | -------- | ----- | ---- | ---------- | ---------|-------|-------|-------|------
1 *Contact information*|||||||||
1.1 Person|Name of the Contact person for the asset|Contact Name|person|maintainer|Yes|See Usage Notes|See Usage Notes|(1,1)|Name should be formatted as Last, First
1.2 Contact Email|Contact person's email address|Contact email|mbox|maintainer_email|Yes|Email address||(1,1)|||
1.3 Organisation (Owner)|The publishing agency.|Publisher|publisher|owner_org|Yes|See Usage Notes|See Usage Notes|(1,1)|Departments and multi-unit agencies may use this field to describe which subordiante agency published this dataset.
1.4 Publisher|-|-|-|-|-|-|-|-|-|
1.5 Author|-|-|-|-|-|-|-|-|-|
1.6 Author Email|-|-|-|-|-|-|-|-|-|
1.7 Maintainer|-|-|-|-|-|-|-|-|-|
1.8 Maintainer Email|-|-|-|-|-|-|-|-|-|
2 *Dataset information*|||||||||
2.1 Unique Identifier|A unique identifier for the dataset or API as maintained within an Agency catalog or database.|Unique Identifier|identifier|id|Yes|See Usage Notes|Characters should be alphanumeric|(1,1)|This field allows third parties to maintain a consistent record for datasets even if title or URLs are updated. Agencies may integrate an existing system for maintaining unique identifiers or enter arbitrary characters for this field. However, each identifier must be unique across the agency’s catalog and remain fixed.|
2.2 Release Date(D)|Date of formal issuance.|Release Date|issued|-|No|Date|Date (YYYY-MM-DD)|(0,1)|
2.3 Modified|-|-|-|-|-|-|-|-|-|
2.4 Last Updated|Most recent date on which the dataset was changed, updated or modified.|Last Update|modified|revision_timestamp|Yes|Date|YYYY-MM-DD|(1,1)|Specify "01" as the day if unknown 
2.5 Description|Human-readable description (e.g. an abstract) but sufficient detail to enable a user to quickly understand whether the asset is of interest.|Description|description|notes|Yes|String|^[a-z0-9_-]{2,}$|(1,1)|
2.6 Keyword|Tags (or keywords) help users discover your dataset, please include terms that would be used by technical and non-technical users.|Tags|keyword|tags|Yes|Separate keywords with commas.|Separate keywords with commas.|(1,n)||Separate keywords with commas
2.7 Frequency of Update|Frequency with which dataset is published|Frequency|accrualPeriodicity|-|No|See Usage Notes|See Usage Notes|(0,1)|Must be one of the following: hourly, daily, weekly, yearly,   Frequency with which dataset is published. |   Must be one of the following: hourly, daily, weekly, yearly, other
2.8 Title | title | Yes | (1,1) | Human-readable name of the asset. Should be in plain English and include sufficient detail to facilitate search and discovery. | string 
2.9 Category    | theme  |  No |  (0,n) |  Main thematic category of the dataset. |   Comma-separated values
3 *Extent information*|||||||||
3.1 Spatial Coverage|The range of spatial applicability of a dataset. Could include a spatial region like a bounding box or a named place.|Spatial|spatial|spatial|If applicable|See Usage Notes||(0,1)|This field should contain one of the following types of content: (1) a bounding coordinate box for the dataset represented in latitude / longitude pairs where the coordinates are specified in decimal degrees and in the order of: minimum longitude, minimum latitude, maximum longitude, maximum latitude; (2) a latitude / longitude pair (in decimal degrees) representing a point where the dataset is relevant; (3) a geographic feature expressed in Geography Markup Language using the Simple Features Profile; or (4) a geographic feature from the GeoNames database.
3.2 Spatial Type|-|-|-|-|-|-|-|-|-|
3.3 Spatial Coordinates|-|-|-|-|-|-|-|-|-|
3.4 Geographic Region Name|-|-|-|-|-|-|-|-|-|
3.5 Geographic Bounding Box - Lower Left Corner|-|-|-|-|-|-|-|-|-|
3.6 Bounding Box - Upper Right Corner|-|-|-|-|-|-|-|-|-|
3.7 Bounding Box - Coordinate Reference System|-|-|-|-|-|-|-|-|-|
3.8 Geographic Bounding Box - Dimensions|-|-|-|-|-|-|-|-|-|
3.9 Temporal Coverage|The range of temporal applicability of a dataset (i.e., a start and end date of applicability for the data).|temporal|temporal|-|If applicable|Time/Date|Dates should be formatted as pairs of {start date, end date} in the format YYYY-MM-DD hh:mm:ss using 24 hour clock time notation (e.g., 2011-02-14 12:00:00, 2013-02-14 12:00:00).|(0,1)|This field should contain an interval of time defined by start and end dates.
3.10 Temporal coverage starts|-|-|-|-|-|-|-|-|-|
3.11 Temporal coverage ends|-|-|-|-|-|-|-|-|-|
3.12 Temporal granularity|-|-|-|-|-|-|-|-|-|
3.13 Temporal granularity factor|-|-|-|-|-|-|-|-|-|
3.14 Periodicity of data collection|-|-|-|-|-|-|-|-|-|
3.15 Periodicity of the production process|-|-|-|-|-|-|-|-|-|
3.16 Periodicity of the estimates|-|-|-|-|-|-|-|-|-|
3.17 Temporal and spatial comparability|-|-|-|-|-|-|-|-|-|
3.18 Periodicity of data dissemination|-|-|-|-|-|-|-|-|-|
3.19 Data Quality|Whether the dataset meets the agency's Information Quality Guidelines.|Data Quality|dataQuality|-|No|Boolean|Boolean (true-false)|(0,1)
3.20 Granularity    | granularity  | No  | (0,1)   | Level of granularity of the dataset.  |    Typically geographical or temporal.
4 *Supplemental information*|||||||||
4.1 Documentation URL|Related documents such as technical information about a dataset, developer documentation, etc.|Related Documents|references|resources|No|Comma-sepated URLs|Comma-sepated URLs|(0,n)|
5 *Distribution information*|||||||||
5.1 Licence|The license dataset or API is published with.|License|license|license_id|If applicable|||(0,1)|
5.2 Copyright|-|-|-|-|-|-|-|-|-|
5.3 Size|The size of the downloadable dataset.|Size|size|-|No|Size|Sizes should be formatted as (e.g.), 52kb, 140mb, 2gb.|(0,1)| 
5.4 URL (R)|URL providing direct access to the downloadable distribution of a dataset|Download URL|accessURL|res_url|If applicable|URL||(1,1)|This must be the direct download URL. Use **landingPage** for landing or disambiguation pages, or **references** for documentation pages.
5.5 Homepage URL|Alternative landing page used to redirect user to a contextual, Agency-hosted “homepage” for the Dataset or API when selecting this resource from the Data.gov user interface|Homepage URL|landingPage|url|No|URL|See Usage Notes|(0,1)|URL; This field is not intended for an agency’s homepage (e.g. www.agency.gov), but rather if a dataset has a human-friendly hub or landing page that users should be directed to for all resources tied to the dataset. This allows agencies to better specify what a visitor receives after selecting one of the agency’s datasets on Data.gov or in third-party mashups.|
5.6 Format | format | If applicable  | (0,1)  |  The file format or API type of the distribution. |   This must describe the exact file available at accessURL using file extensions (e.g., CSV, XLS, XSLX, TSV, JSON, XML). For example, if the download file is a ZIP containing a CSV, the entry here is “ZIP”.
5.7 Language    | language  | No  | (0,n)  | The language of the dataset.  | string
10 *US-specific terms*||||||||| 
Theme|Main thematic category of the dataset.|Category|theme|groups|No|Comma-separated URLs|Comma-separated values    |(0,n)|
Public Access Level|The degree to which this dataset could be made publicly-available, regardless of whether it has been made available. Choices: Public (is or could be made publicly available), Restricted (available under certain conditions), or Private (never able to be made publicly available)|Public Access Level|accessLevel|-|Yes|See Usage Notes|Must be one of the following: Public, Restricted, Private|(1,1)|Must be one of the following: Public, Restricted, Private|
API Endpoint|Endpoint of web service to access dataset.|Endpoint|webService|res_url|If applicable|See Usage Notes||(1,)|This field will serve to delineate the web services offered by an agency and will be used to aggregate cross-government API catalogs.|
RSS Feed|URL for an RSS feed that provides access to the dataset.|RSS Feed|feed|res_url|No|URL||(0,1)|URL; These RSS feeds will be used to create a cross-agency RSS feed search tool.|
Data Dictionary|URL to the data dictionary for the dataset or API. Note that documentation other than a Data Dictionary can be referenced using Related Documents as shown in the expanded fields.|Data Dictionary|dataDictionary|dataDict|If applicable|URL||(1,1)|
System of Records|URL to the System of Records related to this dataset.|System of Records|systemOfRecords|-|No|URL||(0,1)|URL|


**Mappings to Other Vocabs**

Concept|CKAN - Level 1|CKAN - Level 2|CKAN - Level 3|Schema.org|DCAT|ADMS|VoID|Other (e.g. Dublin Core, Foaf, RDF, RDFa Lite)|RDFa Lite 1.1
------- | -------- | ----- | ---- | ---------- | ---------|-------|-------|-------|------
1. *Contact information*    |	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
1.1 Person	|	-	|	-	|	-	|	sdo:Person	|	foaf:Person	|	-	|	-	|	-	|	foaf:person	|
1.2 Contact Email - Publisher	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	foaf:mbox	|
1.2 Contact Email - Dataset	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
1.3 Organisation (Owner)	|	-	|	-	|	-	|	sdo:Organization	|	foaf:Organization	|	-	|	-	|	-	|	dcat:publisher	|
1.4 Publisher	|	-	|	-	|	-	|	sdo:publisher	|	dcterms:publisher	|	dcterms:publisher	|	-	|	-	|	-	|
1.5 Author	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
1.6 Author Email	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
1.7 Maintainer	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
1.8 Maintainer Email	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
2. *Dataset Identification*	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
2.1 Unique Identifier	|	-	|	-	|	-	|	-	|	dcterms:identifier	|	-	|	-	|	-	|	dcterms:identifier	|
2.2 Release Date	|	-	|	-	|	-	|	sdo:datePublished	|	dcterms:issued	|	dcterms:created	|	-	|	-	|	dcterms:issued	|
2.2.R Release Date	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
2.3 Modified	|	-	|	-	|	-	|	sdo:dateModified	|	dcterms:modified	|	dcterms:modified	|	-	|	-	|	-	|
2.3.R Modified	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
2.4 Last Updated	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	dcterms:modified	|
2.4.R Last Updated	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
2.5 Description	|	-	|	-	|	-	|	sdo:description	|	dcterms:description	|	dcterms:description	|	-	|	-	|	dcterms:description	|
2.6 Keyword	|	-	|	-	|	-	|	sdo:keywords	|	dcat:keyword	|	radion:keyword	|	-	|	-	|	dcat:keyword	|
2.7 Frequency of Update	|	-	|	-	|	-	|	-	|	dcat:accuralPeriodicity 	|	-	|	-	|	-	|	dcterms:accrualPeriodicity	|
2.8 Title	|	-	|	-	|	-	|	sdo:name	|	dcterms:title	|	rdfs:label	|	-	|	-	|	dcterms:title	|
2.9 Category	|	-	|	-	|	-	|	sdo:about	|	dcat:theme	|	dcterms:subject	|	-	|	-	|	dcat:theme	|
3. *Extent*	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.1 Spatial coverage	|	-	|	-	|	-	|	ds:spatialCoverage	|	dcterms:spatial	|	dcterms:spatial	|	-	|	-	|	dcterms:spatial	|
3.2 Spatial Type	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.3 Spatial Coordinates	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.4 Geographic Region Name	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.5 Geographic Bounding Box - Lower Left Corner  	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.6 Bounding Box - Upper Right Corner  	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.7 Bounding Box - Coordinate Reference System  	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.8 Geographic Bounding Box - Dimensions  	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.9 Temporal coverage	|	-	|	-	|	-	|	ds:temporalCoverage	|	dcterms:temporal	|	-	|	-	|	-	|	dcterms:temporal	|
3.10 Temporal coverage starts	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.11 Temporal coverage ends	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.12 Temporal granularity	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	dcat:granularity	|
3.13 Temporal granularity factor	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.14 Periodicity of data(set) collection	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.15 Periodicity of the production process	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.16 Periodicity of the estimates	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.17 Temporal and spatial comparability	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.18 Periodicity of data dissemination	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
3.19 Data quality	|	-	|	-	|	-	|	-	|	dcat:dataQuality	|	-	|	-	|	-	|	xsd:boolean	|
3.20 Reference period	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
4. *Supplemental Information*	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
4.1 Documentation URL - resource	|	-	|	-	|	-	|	-	|	dcat:dataDictionary 	|	-	|	-	|	-	|	dcterms:references	|
5. *Distribution Information*	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|	-	|
5.1 Licence	|	-	|	-	|	-	|	-	|	dcterms:license	|	-	|	-	|	-	|	dcterms:license	|
5.2 Copyright	|	-	|	-	|	-	|	sdo:copyrightHolder	|	-	|	-	|	-	|	-	|	-	|
5.3 Size	|	-	|	-	|	-	|	sdo:contentSize	|	dcat:size	|	-	|	-	|	-	|	dcat:size	|
5.4 URL - resource	|	-	|	-	|	-	|	sdo:contentUrl	|	dcat:accessURL	|	adms:accessURL	|	-	|	-	|	dcat:accessURL	|
5.5 Homepage URL	|	-	|	-	|	-	|	sdo:url	|	foaf:homepage	|	-	|	-	|	-	|	dcat:landingPage	|
5.6 Format - resource	|	-	|	-	|	-	|	sdo:encodingFormat	|	dcterms:format	|	dcterms:format	|	-	|	-	|	dcterms:format	|
5.7 Language	|	-	|	-	|	-	|	sdo:inLanguage	|	dcterms:language	|	dcterms:language	|	-	|	-	|	dcat:language	|

**Example JSON Excerpt**

[
    {
        "title": "Data Catalog",
        "description": "Version 1.0", 
        "keyword": "catalog", 
        "modified": "2013-05-09 06:00:00",
        "publisher": "US Department of X",
        "person": "Contact Person",
        "mbox": "contact.person@agency.gov",
        "identifier": "1",
        "accessLevel": "public",
        "distribution": [
            {
                "accessURL": "http://agency.gov/data.json",
                "format": "json"
            }
        ]  
    },
    {
        "title": "Public Elementary/Secondary Listing",
        "description": "The purpose of the CCD nonfiscal surveys is to provide a listing of all schools and agencies providing free public elementary and secondary education, along with basic descriptive statistical information on each school and agency listed. Penalties apply for misuse, seehttp://nces.ed.gov/ncesglobal/data_usage_agreement.aspfor more details.", 
        "keyword": "education, schools", 
        "modified": "2011-11-19 00:00:00",
        "publisher": "US Department of Education",
        "person": "Open Data Initiative",
        "mbox": "opendata@ed.gov",
        "identifier": "ykv5-fn9t",
        "accessLevel": "public",
        "dataDictionary": "http://nces.ed.gov/ccd/pdf/INsc09101a.pdf",
        "distribution": [
            {
                "accessURL": "https://explore.data.gov/views/ykv5-fn9t/rows.csv?accessType=DOWNLOAD", 
                "format": "csv",
                "size": "200mb"
            }, 
            {
                "accessURL": "https://explore.data.gov/views/ykv5-fn9t/rows.json?accessType=DOWNLOAD", 
                "format": "json"
            }, 
            {
                "accessURL": "https://explore.data.gov/views/ykv5-fn9t/rows.xml?accessType=DOWNLOAD", 
                "format": "xml"
            }
        ],
        "webService": "http://explore.data.gov/api/views/ykv5-fn9t/rows.json", 
        "license": "Public Domain", 
        "spatial": "US", 
        "temporal": "2009-09-01 00:00:00,2010-05-31 00:00:00", 
        "issued": "",
        "frequency": "one-time",
        "language": "English", 
        "granularity": "",
        "dataQuality": "true",
        "theme": "education", 
        "references": "http://nces.ed.gov/ccd/data/txt/psu091alay.txt", 
        "landingPage": "http://ed.gov/developer",
        "feed": "",
        "systemOfRecords": "http://nces.ed.gov/ccd/"     
    }]


**Mapping**
Please find the metadata mapping index between G8 nations [here](https://github.com/nsinai/G8_Metadata_Mapping/blob/master/index.md).

**Feedback**
Please give feedback on this mapping - you can fill out a [short survey (5 questions)](http://www.surveymonkey.com/s/CCM3F2C) or a [longer survey (10 questions)](http://www.surveymonkey.com/s/N2ZMP7K).

