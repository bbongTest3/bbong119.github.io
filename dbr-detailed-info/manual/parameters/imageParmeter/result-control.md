---
layout: manual-parameter
id: parameter_image_result
sourceCodeUrl: /dbr-detailed-info/manual/parameters/imageParmeter/result-control.md
---

# ImageParameter Object - Result Control Parameters

 | Parameter Name | Description |
 | -------------- | ----------- | 
 | [`ImageParameter.IntermediateResultTypes`](#intermediateresulttypes) | Sets which types of intermediate result to be kept for further reference. Intermediate result types can be combined. | 
 | [`ImageParameter.IntermediateResultSavingMode`](#intermediateresultsavingmode) | Sets the mode for saving the intermediate result. | 
 | [`ImageParameter.ResultCoordinateType`](#resultcoordinatetype) | Specifies the format for the coordinates returned | 
 | [`ImageParameter.TextResultOrderModes`](#textresultordermodes) | Sets the mode and priority for the order of the text results returned. | 
 | [`ImageParameter.ReturnBarcodeZoneClarity`](#returnbarcodezoneclarity) | Sets whether or not to return the clarity of the barcode zone. |  
 
---

## IntermediateResultTypes
Sets which types of intermediate result to be kept for further reference. Intermediate result types can be combined.  

### As Json Parameter

| Json Object |	Json Parameter Name | Value Type | Value Range | Default Value |
| ----------- | ------------------- | ---------- | ----------- | ------------- |
| ImageParameter | IntermediateResultTypes | *string Aarry* | An array item can be any one of the [`IntermediateResultTypes` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresulttype) items | `null` |

**Json Parameter Example**   
```
{
    "IntermediateResultTypes": [
        "IRT_BINARIZED_IMAGE",
        "IRT_ORIGINAL_IMAGE"
    ]
}
```

### As `PublicRuntimeSettings` Member

| Struct |	Struct Member Name | Value Type | Value Range | Default Value |
| ------ | ------------------ | ---------- | ----------- | ------------- |
| [`PublicRuntimeSettings`]({{ site.manual_interface_struct }}PublicRuntimeSettings.html) | [`intermediateResultTypes`]({{ site.manual_interface_struct }}PublicRuntimeSettings.html#intermediateresulttypes) | *int* | A combined value of [`IntermediateResultType` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresulttype) items. | `IRT_NO_RESULT` (0) |

**See Also**   
- [`PublicRuntimeSettings` Struct]({{ site.manual_interface_struct }}PublicRuntimeSettings.html)
- [`IntermediateResultType` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresulttype)



&nbsp;




## IntermediateResultSavingMode
Sets the mode for saving the intermediate result.

### As Json Parameter

| Json Object |	Json Parameter Name | Value Type | Default Value |
| ----------- | ------------------- | ---------- | ------------- |
| ImageParameter | IntermediateResultSavingMode | *JSON Object or string* | `"IRSM_MEMORY"` |

**Remarks**   
- As a string, the value can be any one of the [`IntermediateResultSavingMode` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresultsavingmode) items.   

- As a JSON Object, it contains keys - `Mode`, `FolderPath`, `RecordsetSizeOfLatestImages`. `Mode` is **mandatory** and its value can be any one of the [`IntermediateResultSavingMode` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresultsavingmode) items. Other keys please check [arguments of `IntermediateResultSavingMode`]({{ site.manual_interface_argument}}IntermediateResultSavingMode.html) for available settings.   

**Json Parameter Example**   
```
{
    "IntermediateResultSavingMode":"IRSM_MEMORY",
}
or
{
    "IntermediateResultSavingMode": {
            "Mode"": ""IRSM_FILESYSTEM",
            "FolderPath": "C:\", 
        }
}
or
{
    "IntermediateResultSavingMode":"IRSM_FILESYSTEM(C:\)",
}
```

**See Also**
- [`IntermediateResultSavingMode` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresultsavingmode)
- [Arguments of `IntermediateResultSavingMode`]({{ site.manual_interface_argument}}IntermediateResultSavingMode.html)



### As `PublicRuntimeSettings` Member

| Struct |	Struct Member Name | Value Type | Value Range | Default Value |
| ------ | ------------------ | ---------- | ----------- | ------------- |
| [`PublicRuntimeSettings`]({{ site.manual_interface_struct }}PublicRuntimeSettings.html) | [`intermediateResultSavingMode`]({{ site.manual_interface_struct }}PublicRuntimeSettings.html#intermediateresultsavingmode) | [`IntermediateResultSavingMode`]({{ site.manual_interface_enum }}result-enum.html#intermediateresultsavingmode) | Any one of the [`IntermediateResultSavingMode` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresultsavingmode) items.| `IRSM_MEMORY`|

**See Also**   
- [`PublicRuntimeSettings` Struct]({{ site.manual_interface_struct }}PublicRuntimeSettings.html)
- [`IntermediateResultSavingMode` Enumeration]({{ site.manual_interface_enum }}result-enum.html#intermediateresultsavingmode)



&nbsp;






