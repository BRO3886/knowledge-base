# Random Code Snippets

## Download attendance from airmeet

```json
//get the class elements for attendees
const d = document.getElementsByClassName("attendee-desc")

//append values to string
var s = "";
for(i=0;i<d.length;i++){
s+=d[i].innerText+"\n";
}

//convert to csv
let csvContent = "data:text/csv;charset=utf-8," +s;
var encodedUri = encodeURI(csvContent);

//create element on dom and click to download
var link = document.createElement("a");
link.setAttribute("href", encodedUri);
link.setAttribute("download", "attendance.csv");
document.body.appendChild(link);
link.click();
```