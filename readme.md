# T24UserTool

T24USerTool is an Excel workbook containing macros in VBA, that connects to T24 Transact Banking Software to perform various useful actions.

## Installation
Extract the files. User_v7_x.xlsx is the tool, the documentation is in the form of a Word document, USERManagementTool_v7_x

It connects to T24 using HTTP-GET (up to R16) or HTTP-POST (R17 and later) to perfom OFS requests.
You need to be able to create a jboss-user in T24.
It needs a reference to Microsofts MSXML2 library.

```VBA
Set myRequest = New MSXML2.XMLHTTP60
myRequest.Open "POST", gsURL_R18, False, gsJBossUser, gsJBossPwd
myRequest.setRequestHeader "Content-Type", "application/x-www-form-urlencoded"
On Error GoTo no_http_send
myRequest.send ("ofsRequest=" & sOFS)
```

## Usage

The following actions can be done with the tool:
* Create users
* Password reset
* Execute OFS commands
* Update EB.LOOKUP table
* Extract Updates documentation
* Generate Data Dictionary
* Generate sample OFSML
* Maintain EB.USER.ROLES and USER.SMS.GROUPS
* List INAU records and authorise
* Translate online HelpText
* DataDownload (fill TAABS-like excel)

## Screenshots
*Tranlation of helptext (includes using automatic translation with Google Translate and Microsoft Translator):*
![screenshot helptext translation](/images/HelpTextTranslate.jpg)

*Download full tables (here TRANSACTION table) from T24:*
![screenshot Data download](/images/DownloadData.jpg)

## Contributing
Pull requests are welcome. 
For issues, please open an issue or request.

## License
None