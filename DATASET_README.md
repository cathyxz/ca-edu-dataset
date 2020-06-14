This is the original README file for this dataset, converted to markdown for readability.

# Readme for the 2018–19 Unaudited Actual Financial Data

For fiscal year 2018–19, 1,587 local educational agencies (LEAs) (991 districts, 538 charter schools, and 58 county offices of education) in California submitted their yearend unaudited actual (UA) financial data using the standardized account code structure (SACS).

The self-extracting zipped file sacs1819.exe contains two files: this readme file (sacs1819readme.docx) and a Microsoft Access database, sacs1819.mdb. When executed, the files are extracted onto your PC into the default subdirectory C:\1819SACS\Data. (You can change the extract directory.)

For more information related to the SACS, visit the California Department of Education’s SACS web page: https://www.cde.ca.gov/fg/ac/ac/.
Notes:
1. The Charters table includes charter schools’ K–12 average daily attendance (ADA).
2. The K–12 ADA in the LEAs table located within the SACS database do not include 3.ADA for charter schools that filed UA data in their authorizing agency’s General Fund (Fund 01).
3. The county and state totals are located in a separate table: UserGL_Totals.

## File Layouts for the Access Database
### UserGL
General ledger information submitted by LEAs that have a SACS based accounting system.

| Field          |   Data Type  |   Width           |   Description                                        |   |
|----------------|--------------|-------------------|------------------------------------------------------|---|
|   Ccode        |   Text       |   2               |   County Code                                        |   |
|   Dcode        |   Text       |   5               |   District Code                                      |   |
|   SchoolCode   |   Text       |   7               |   School Code                                        |   |
|   Fiscalyear   |   Text       |   4               |   Fiscal Year                                        |   |
|   Period       |   Text       |   4               |   Report Period Identifier ('A') = Unaudited Actual  |   |
|   Colcode      |   Text       |   4               |   Column Code Identifier ('BA') = Unaudited Actual   |   |
|   Account      |   Text       |   19              |   SACS Account Code                                  |   |
|   Fund         |   Text       |   2               |   SACS Fund Code                                     |   |
|   Resource     |   Text       |   4               |   SACS Resource Code                                 |   |
|   Projectyear  |   Text       |   1               |   Project Year (for federally funded projects)       |   |
|   Goal         |   Text       |   4               |   SACS Goal                                          |   |
|   Function     |   Text       |   4               |   SACS Function                                      |   |
|   Object       |   Text       |   4               |   SACS Object Code                                   |   |
|   Value        |   Number     |   Decimal (18,2)  |   Amount                                             |   |


### UserGL_Totals

General ledger information submitted by LEAs that have a SACS based accounting system. Totals are by counties and state. Ccode and Dcode (“999” + Ccode) identify the counties’ subtotals. Ccode of “99” and Dcode of “99999” identify the state totals.

|   Field        |   Data Type  |   Width           |   Description                                        |
|----------------|--------------|-------------------|------------------------------------------------------|
|   Ccode        |   Text       |   2               |   County Code                                        |
|   Dcode        |   Text       |   5               |   District Code                                      |
|   Fiscalyear   |   Text       |   4               |   Fiscal Year                                        |
|   Period       |   Text       |   4               |   Report Period Identifier ('A') = Unaudited Actual  |
|   Colcode      |   Text       |   4               |   Column Code Identifier ('BA') = Unaudited Actual   |
|   Account      |   Text       |   19              |   SACS Account Code                                  |
|   Fund         |   Text       |   2               |   SACS Fund Code                                     |
|   Resource     |   Text       |   4               |   SACS Resource Code                                 |
|   Projectyear  |   Text       |   1               |   Project Year (for federally funded projects)       |
|   Goal         |   Text       |   4               |   SACS Goal                                          |
|   Function     |   Text       |   4               |   SACS Function                                      |
|   Object       |   Text       |   4               |   SACS Object Code                                   |
|   Value        |   Number     |   Decimal (18,2)  |   Amount                                             |


## Look-up Description Tables
### LEAs

Information on county offices of education, common administrative districts, joint powers agencies, and elementary, high, and unified school districts that filed in SACS for fiscal year 2018–19.

|   Field Name  |   Data Type  |   Width   |   Description               |
|---------------|--------------|-----------|-----------------------------|
|   Ccode       |   Text       |   2       |   County Code               |
|   Dcode       |   Text       |   5       |   District Code             |
|   Dname       |   Text       |   75      |   District Name             |
|   Dtype       |   Text       |   15      |   District Type             |
|   K12ADA      |   Number     |   Double  |   Average Daily Attendance  |

### Fund
SACS Fund codes included in the UserGL data.

|   Field  |   Data Type  |   Width  |   Description       |
|----------|--------------|----------|---------------------|
|   Code   |   Text       |   4      |   Fund Code ID      |
|   Title  |   Text       |   250    |   Fund Description  |


### Resource
SACS Resource codes included in the UserGL data.

|   Field  |   Data Type  |   Width  |   Description           |
|----------|--------------|----------|-------------------------|
|   Code   |   Text       |   4      |   Resource Code ID      |
|   Title  |   Text       |   250    |   Resource Description  |


### Goal
SACS Goal codes included in the UserGL data.

|   Field  |   Data Type  |   Width  |   Description       |
|----------|--------------|----------|---------------------|
|   Code   |   Text       |   4      |   Goal Code ID      |
|   Title  |   Text       |   250    |   Goal Description  |

### Function
SACS Function codes included in the UserGL data.

|   Field  |   Data Type  |   Width  |   Description           |
|----------|--------------|----------|-------------------------|
|   Code   |   Text       |   4      |   Function Code ID      |
|   Title  |   Text       |   250    |   Function Description  |

### Object
SACS Object codes included in the UserGL data.

|   Field  |   Data Type  |   Width  |   Description         |
|----------|--------------|----------|-----------------------|
|   Code   |   Text       |   4      |   Object Code ID      |
|   Title  |   Text       |   250    |   Object Description  |

### Charters
The Charters table contains information about the Charter Schools that filed using either SACS or the Charter School Alternative Form (sometimes called the Charter Alt Form), as well as those that did not file year-end unaudited actual financial data for fiscal year 2018–19.

|   Field Name     |   Data Type  |   Width   |   Description               |
|------------------|--------------|-----------|-----------------------------|
|   Ccode          |   Text       |   2       |   County Code               |
|   Dcode          |   Text       |   5       |   District Code             |
|   SchoolID       |   Text       |   7       |   School Code               |
|   CharterNumber  |   Text       |   10      |   Charter Number            |
|   CharterName    |   Text       |   100     |   Charter Name              |
|   ReportType     |   Text       |   100     |   Report Type               |
|   ReportLevel    |   Text       |   30      |   Report Level              |
|   FundUsed       |   Text       |   30      |   Fund Used                 |
|   K12ADA         |   Number     |   Double  |   Average Daily Attendance  |

Report Type: Alt Form (759 rows), SACS (538 rows) (total that reported in the Alt Form or SACS: 1,297 rows), or Did not report (25 rows).

Report Level: County Office of Education (COE) (43 rows), District (302 rows), School (916 rows), or “State Board” for State Board of Education (36 rows) (total that reported separately by school, including State Board: 952 rows).
Fund Used (if reported in SACS): “62 Charter Enterprise” for Fund 62, Charter Schools Enterprise Fund (165 rows); “09 Charter Spec. Revenue” for Fund 09, Charter Schools Special Revenue Fund 186 rows); or “01 General” for Fund 01, General Fund/County School Service Fund (187 rows).

If you have suggestions for what information we might add that would make your analyses easier to perform, please contact Financial Accountability & Information Services by phone at 916-322-1770 or by email at sacsinfo@cde.ca.gov.
