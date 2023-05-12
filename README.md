# GoogleSheetHelper

The GoogleSheet.Helper namespace was built because I struggled to read from a Google Sheet in C#, so I wanted to make it easier for other people to do this.

## Features

GoogleSheet.Helper has one class named GoogleSheetHelper, the fields are as follows:

| field | Type | Description | Protection Level |
| --------- | ---- | ----------- | ---------------- |
| `SheetID` | `string` | The ID of the Google Sheet you want to read from. | private |
| `ApplicationName` | `string` | The name of the application you are using the Google Sheet in. | private |
| `credentials` | `string` | The path (or filename) to your cridentials.json file | private |
| `c` | `GoogleCredential` | The GoogleCredential object that is used to authenticate the Google Sheet. | private |
| `service` | `SheetsService` | The SheetsService object that is used to read from the Google Sheet. | private |

The GoogleSheetHelper class has one constructor, the parameters are as follows, in order of how you input them:

| Parameter | Type | Description |
| --------- | ---- | ----------- |
| `SheetID` | `string` | The ID of the Google Sheet you want to read from. |
| `credentialsPath` | `string` | The path (or filename) to your cridentials.json file |
| `ApplicationName` | `string` | The name of the application you are using the Google Sheet in. |

The GoogleSheetHelper class has several methods, the methods are as follows:

| Method | Return Type | Parameters | Description |
| ------ | ----------- | --------- | ----------- |
| `WriteToCell` | `bool` | `string` writeValue, `string` index | Writes the `writeValue` to the given `index`, in A1 notation |
| `SearchAtIndex` | `string` | `string` searchFor, `string` indexRange | Searches the index range until it finds the given string to `searchFor` |
| `ReadFromCell` | `string` | `string` index | Reads the value from the given `index`, in A1 notation | 
| `InitializeSheetsService` | `SheetsService` | none | A private method to make a new `SheetsService` for the helper class to use |

## Usage

To use the GoogleSheetHelper class, you must first create a new GoogleSheetHelper object, like so (After Downloading the [nuget package](https://www.nuget.org/packages/GoogleSheetHelper/)):

```csharp
using GoogleSheet.Helper;

public class Program {

    public static void Main(string[] args) {
        GoogleSheetHelper helper = new GoogleSheetHelper("<YourSheetID>", "<Cridentials.jsonPath>", "<YourApplicationName>");

    }


}
```

Thanks for using my project, I hope it helps you as much as it helped me!

(c) 2023 - 2023, [Gammer0909](https://github.com/Gammer0909/)
