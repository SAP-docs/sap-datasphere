<!-- loio70ffed417b054b4692458edbd56c90f5 -->

# System Requirements and Technical Prerequisites

SAP Datasphere is a fully web-based offering. You will need an internet connection and a system that meets certain requirements.



The requirements listed here are for the current release.



<a name="loio70ffed417b054b4692458edbd56c90f5__section_i1q_scr_tcb"/>

## Client Software Requirements


<table>
<tr>
<th valign="top">

Client Software

</th>
<th valign="top">

Version

</th>
<th valign="top">

Additional Information

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Desktop browser

</td>
<td valign="top">

Google Chrome, latest version

</td>
<td valign="top">

Google releases continuous updates to their Chrome browser. We make every effort to fully test and support the latest versions as they are released. However, if defects are introduced with OEM-specific browser software, we cannot guarantee fixes in all cases.

For additional system requirements, see your web browser documentation.

</td>
</tr>
<tr>
<td valign="top">

Microsoft Edge based on the Chromium engine, latest version

</td>
<td valign="top">

Microsoft has available for download continuous updates to their new Chromium-based Edge browser. We make every effort to fully test and support the latest versions as they are released.

</td>
</tr>
<tr>
<td valign="top">

Additional software

</td>
<td valign="top">

Adobe Acrobat Reader 9 or higher

</td>
<td valign="top">

\-

</td>
</tr>
</table>



<a name="loio70ffed417b054b4692458edbd56c90f5__section_j1q_scr_tcb"/>

## Client Configuration Requirements


<table>
<tr>
<th valign="top">

Client Configuration

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Additional Information

</th>
</tr>
<tr>
<td valign="top">

Network bandwidth

</td>
<td valign="top">

Minimum 500-800 kbit/s per user

</td>
<td valign="top">

In general, SAP Datasphere requires no more bandwidth than is required to browse the internet. All application modules are designed for speed and responsiveness with minimal use of large graphic files.

</td>
</tr>
<tr>
<td valign="top">

Screen resolution

</td>
<td valign="top">

XGA 1024x768 \(high color\) or higher

Widescreen: 1366x766 or higher

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Minimum recommended browser cache size

</td>
<td valign="top">

250 MB

</td>
<td valign="top">

SAP Datasphere is a Web 2.0 application. We recommend allowing browser caching because the application uses it heavily for static content such as image files. If you clear your cache, the browser will not perform as well until the deleted files are downloaded again to the browser and cached for use next time.

To set browser cache size, see your browser documentation.

</td>
</tr>
<tr>
<td valign="top">

HTTP 1.1

</td>
<td valign="top">

Enable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

JavaScript

</td>
<td valign="top">

Enable

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Cookies

</td>
<td valign="top">

Enable web browser session cookies \(non-persistent\) for authentication purposes

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Pop-up windows

</td>
<td valign="top">

Allow pop-up windows from SAP Datasphere domains

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Power Option Recommendation

</td>
<td valign="top">

High Performance mode for improved JavaScript performance

</td>
<td valign="top">

For Microsoft based Operating Systems

</td>
</tr>
</table>



<a name="loio70ffed417b054b4692458edbd56c90f5__section_isq_lgd_wz"/>

## Supported Languages


<table>
<tr>
<th valign="top">

Client Browser

</th>
<th valign="top">

What's Supported

</th>
</tr>
<tr>
<td valign="top">

Menus, buttons, messages, and other elements of the user interface.

</td>
<td valign="top">

Bulgarian \(bgBG\); Catalan \(caES\); Chinese \(zhTW\); Chinese \(Simplified\) \(zhCN\); Croatian \(hrHR\); Czech \(csCZ\); Danish \(daDK\); Dutch \(nlNL\); English \(enGB\); English \(enUS\); Estonian \(etEE\); French \(frCA\); French \(frFR\); Finnish \(fiFI\); German \(deDE\); German \(deCH\); Greek \(elGR\); Hindi \(hiIN\); Hungarian \(huHU\); Indonesian \(idID\); Italian \(itIT\); Japanese \(jaJP\); Kazakh \(kkKZ\); Korean \(koKR\); Latvian \(lvLV\); Lithuanian \(ltLT\); Macedonian \(mk-MK\); Malay \(msMY\); Montenegrin \(cnr-ME\); Norwegian \(noNO\); Polish \(plPL\); Portuguese \(Brazil\) \(ptBR\); Portuguese \(Portugal\) \(ptPT\); Romanian \(roRO\); Russian \(ruRU\); Serbian \(srRS\); Serbian Cyrillic \(sr-Cyrl-RS\); Slovakian \(skSK\); Slovenian \(slSL\); Spanish \(esES\); Spanish \(esMX\); Swedish \(svSE\); Thai \(thTH\); Turkish \(trTR\);Ukrainian \(ukUA\); Vietnamese \(viVN\) and Welsh \(cyGB\).

</td>
</tr>
</table>



<a name="loio70ffed417b054b4692458edbd56c90f5__section_cpx_p1d_yy"/>

## Data Connectivity



### Connectivity with SAP HANA Smart Data Integration

We recommend to always use the latest released version of the Data Provisioning Agent but at least the recommended minimum version from SAP Note [2419138](https://me.sap.com/notes/2419138). Make sure that all agents that you want to connect to SAP Datasphere have the same latest version.

For more information, including information on minimum requirements for source systems and databases, see:

-   [SAP HANA Smart Data Integration Product Availability Matrix \(PAM\)](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf)

-   [Configure Data Provisioning Adapters](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/6ed502701abd4d1ca94d463d7dc6e99f.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation


