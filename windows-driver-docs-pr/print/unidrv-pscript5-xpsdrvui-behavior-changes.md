---
title: Unidrv/PScript5 XPSDrv UI Behavior Changes
author: windows-driver-content
description: Unidrv/PScript5 XPSDrv UI Behavior Changes
MS-HAID:
- 'xpsconfig\_c363a98e-71cd-4fd6-9da2-648b3c6af562.xml'
- 'print.unidrv\_pscript5\_xpsdrvui\_behavior\_changes'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7c594f40-8e75-4c8b-a60e-42f74116c75f
---

# Unidrv/PScript5 XPSDrv UI Behavior Changes


A Unidrv/PScript5 driver that is running in XPSDrv mode will create the following core driver default UI behavior changes. (In the following table, "PS only" means the behavior change is specific to a PScript5 driver. "Unidrv only" means the behavior change is specific to Unidrv driver. If both of these phrases do not appear, the behavior change applies to both Unidrv and PScript5 drivers.)

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI</th>
<th>Non-XPSDrv behavior</th>
<th>XPSDrv behavior</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Orientation</p>
<p>(<strong>Layout</strong> tab)</p></td>
<td><p>(PS only) The hard-coded UI has three options: Portrait, Landscape, and Rotated Landscape.</p></td>
<td><p>(PS only) The hard-coded Orientation UI is not displayed.</p></td>
</tr>
<tr class="even">
<td><p>Copy Count</p>
<p>(<strong>Advanced</strong> tab)</p></td>
<td><p>(Unidrv only) The Copy Count UI is always displayed unless the GPD file has a &quot;Collate&quot; feature with &quot;*ConcealFromUI?: TRUE&quot;:</p>
<p>(Unidrv only) When EMF is enabled, the Copy Count UI is hard-coded to have an upper limit that is the maximum value of 9999 or the GPD file's specified *MaxCopies value.</p>
<p>(Unidrv only) When EMF is disabled, Copy Count has an upper limit of the GPD file *MaxCopies value.</p>
<p>(PS only) The Copy Count UI is always displayed, with an upper limit that is hard-coded to be 9999.</p></td>
<td><p>(Unidrv only) The Copy Count UI behaves the same as the non-XPSDrv behavior with EMF disabled.</p>
<p>(PS only) Copy Count is always displayed, with an upper limit that is specified in the PPD file's *MSXPSMaxCopies value. The upper limit is set to 1 if the PPD file does not specify *MSXPSMaxCopies.</p></td>
</tr>
<tr class="odd">
<td><p>Collated</p>
<p>(<strong>Advanced</strong> tab)</p></td>
<td><p>When EMF is enabled, the Collated UI (which is a check box next to Copy Count) is hard-coded to be displayed.</p>
<p>When EMF is disabled, Collated is displayed only if the GPD or PPD file specifies &quot;Collate&quot; as a supported feature, and the &quot;Collate&quot; GPD or PPD feature is not constrained by any device setting features.</p></td>
<td><p>The Collated UI behaves the same as the non-XPSDrv behavior with EMF disabled.</p></td>
</tr>
<tr class="even">
<td><p>Color</p>
<p>(<strong>Paper/Quality</strong> tab)</p></td>
<td><p>(Unidrv only) The color versus black and white UI selection is shown if the GPD ColorMode feature has one color option.</p></td>
<td><p>(Unidrv only) The color versus black and white UI selection is shown if the GPD ColorMode feature has one color option and if the ColorMode feature does not specify &quot;*ConcealFromUI?: TRUE&quot;.</p></td>
</tr>
<tr class="odd">
<td><p>ICM Method, ICM Intent</p>
<p>(<strong>Advanced</strong> tab)</p></td>
<td><p>The ICM Method UI has three hard0coded options for Unidrv: disabled, by host, or by driver. This UI has one more hard-coded option for PScript5 drivers by device.</p>
<p>The ICM Intent UI has four hard-coded options: Graphics, Picture, Proof, or Match.</p></td>
<td><p>The hard-oded ICM Method and ICM Intent UI are not displayed.</p></td>
</tr>
<tr class="even">
<td><p>Scaling</p>
<p>(<strong>Advanced</strong> tab)</p></td>
<td><p>Unidrv does not show the Scaling UI.</p>
<p>PScript5 driver shows the Scaling UI with a hard-coded range (1%-1000%).</p></td>
<td><p>The hard-coded Scaling UI is not be displayed. You can define a generic GPD or PPD scaling feature (which is shown in the Advanced tree view UI) or provide a custom scaling UI.</p></td>
</tr>
<tr class="odd">
<td><p>TrueType Font</p>
<p>(<strong>Advanced</strong> tab)</p></td>
<td><p>The hard-coded TrueType Font UI has two options: Substitute with Device Font or Download as Softfont.</p></td>
<td><p>The hard-coded TrueType Font UI is not displayed.</p></td>
</tr>
<tr class="even">
<td><p>Pages Per Sheet</p>
<p>(<strong>Layout</strong> tab)</p></td>
<td><p>For Unidrv, when EMF is enabled, the Pages Per Sheet UI shows seven hard-coded options: 1, 2, 4, 6, 9, 16, and Booklet.</p>
<p>For PScript5, the UI shows seven hard-coded options: 1, 2, 4, 6, 9, 16, and Booklet.</p></td>
<td><p>The hard-coded Pages Per Sheet UI is not displayed.</p></td>
</tr>
<tr class="odd">
<td><p>Other EMF Simulation Features</p>
<p>(various tabs)</p></td>
<td><p>Other EMF simulation features show up in the following locations:</p>
<ul>
<li>In the Layout tab,
<ul>
<li>Winprint-based NUp Border UI check box</li>
<li>Winprint-based Page Order UI with two hardcoded options: Front to Back and Back to Front.</li>
</ul></li>
<li>In the Advanced tab:
<ul>
<li>Hardcoded &quot;Advanced Printing Features&quot; with two options: Enabled or Disabled.</li>
<li>Winprint-based NUp Direction UI with four options: Right-then-Down, Down-then-Right, Left-then-Down, Down-then-Left.</li>
<li>Winprint-based Booklet Edge UI.</li>
</ul></li>
</ul></td>
<td><p>None of the hard-coded or winprint-based EMF simulation features are displayed.</p></td>
</tr>
<tr class="even">
<td><p>Rendering Features by Unidrv</p>
<p>(various tabs)</p></td>
<td><p>(Unidrv only) Rendering features are hard-coded in two locations: Quality Macro UI (on Paper/Quality tab) and Print Text as Graphics (on Advanced tab).</p></td>
<td><p>(Unidrv only) None of the hard-coded Unidrv rendering features are displayed.</p></td>
</tr>
<tr class="odd">
<td><p>Rendering Features by PScript5</p>
<p>(<strong>Advanced</strong> tab)</p></td>
<td><p>(PS only) Hard-coded &quot;PostScript Options&quot; include: PostScript Output Option, TrueType Font Download Option, PostScript Language Level, Send PostScript Error Handler, Mirrored Output, and Negative Output.</p></td>
<td><p>(PS only) None of the hard-coded PS rendering features are displayed.</p></td>
</tr>
<tr class="even">
<td><p>Form-Tray Assignment Table</p>
<p>(<strong>DeviceSettings</strong> tab)</p></td>
<td><p>The Form-Tray Assignment Table is always displayed to enable administrators to select the form-to-tray assignment.</p></td>
<td><p>The core Unidrv or PScript5 driver does not display the form-tray assignment table UI. You can provide a custom UI.</p></td>
</tr>
<tr class="odd">
<td><p>Font Substitution Table</p>
<p>(<strong>DeviceSettings</strong> tab)</p></td>
<td><p>The Font Substitution Table is always displayed to enable administrators to select the TrueType font-to-Device font substitution.</p></td>
<td><p>The core Unidrv or PScript5 driver does not display the font substitution table UI. Vendor plug-ins can provide their own custom UI.</p></td>
</tr>
<tr class="even">
<td><p>Device Features by Unidrv</p>
<p>(<strong>DeviceSettings</strong> tab)</p></td>
<td><p>(Unidrv only) The hard-coded feature UI includes</p>
<p>Font Cartridge or External font installer.</p></td>
<td><p>(Unidrv only) None of the hard-coded Unidrv device features are displayed.</p></td>
</tr>
<tr class="odd">
<td><p>Device Features by PScript5</p>
<p>(<strong>DeviceSettings</strong> tab)</p></td>
<td><p>(PS only) The hard-coded feature UI includes: Available PostScript Memory, Output Protocol, Send CTRL-D Before/After, Convert Gray Text, Convert Gray Graphics, Add Euro Currency, Job Timeout, Wait Timeout, Minimum Font Size to Download as Outline, and Maximum Font Size to Download as Bitmap.</p></td>
<td><p>(PS only) None of the hard-coded PS device features are displayed.</p></td>
</tr>
</tbody>
</table>

 

 

 


--------------------
[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bprint\print%5D:%20Unidrv/PScript5%20XPSDrv%20UI%20Behavior%20Changes%20%20RELEASE:%20%289/1/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")


