## Onedrive Embed

The quick and easy method but less flexible is to do the following

1. In a browser go to your https://onedrive.live.com and right click on the Excel file and then select embed.
2. Click 'generate' button.
	* > :bulb: You can then just copy the iframe code in the text box
	and paste it in to your document if desired but will loose the features you get below.
3. At bottom of panel click `Customize how this embedded workbook`.
4. In new window click the `javascript` tab above the textbox at bottom.
5. copy & paste all of it temporarily as the textbox is stupidly small
6. about 12 lines down locate the `var fileToken = ....` and copy the long code inside the quotes but don't copy the quotes themselves
5. paste it into a divs `data-excel-token` attribute as seen in the html example below

**simple example**
```html
<div
data-excel-token="SDF4E541E7F8747E1B!395/-800160894226760165/t=0&s=0&v=!ANZtfYbhiHy1ASg">
</div>
```

Will produce ...


<div
data-excel-token="SDF4E541E7F8747E1B!395/-800160894226760165/t=0&s=0&v=!ACxW3W7JLW28c3M" >
</div>
[source](https://excel.officeapps.live.com/x/_layouts/xlembedconfigurator.aspx?Fi=SDF4E541E7F8747E1B!395&C=5_810_DM2-SKY-WAC-WSHI&ui=en-US&rs=en-US&su=-800160894226760165&ak=t%3d0%26s%3d0%26v%3d!ACxW3W7JLW28c3M&E=1)

a more complicated example setting default zoom , using a range, default cell selection and centered. the height and width are what the excel embed page uses and calced for us.
class='center' will make sure it centers on the page.

**Income Snapshot**{.center}

<div data-excel-token="SDF4E541E7F8747E1B!395/-800160894226760165/t=0&s=0&v=!ACxW3W7JLW28c3M"
data-range="'Financial Report'!B5:F18"
data-selected-cell="'Financial Report'!B5"
data-show-toolbar="false"
width="515"
height="413"
class="center">
</div>

source
```html
**Income Snapshot**{.center}

<div data-excel-token="SDF4E541E7F8747E1B!395/-800160894226760165/t=0&s=0&v=!ACxW3W7JLW28c3M"
data-range="'Financial Report'!B5:F18"
data-selected-cell="'Financial Report'!B5"
data-show-toolbar="false"
width="515"
height="413"
class="center">
</div>
```

## Options


```html
<div data-excel-token="the key, see above for getting it"
data-zoom="the number as a percentage without the %"
data-range="the sheet and cell range to show"
data-selected-cell="what sheet and cell should be selected by default"
data-show-toolbar="show the toolbar above the doc">
</div>
```
