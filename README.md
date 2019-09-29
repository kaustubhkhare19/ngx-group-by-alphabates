# ngx-group-by-alphabates
Angular library - Group by your list alphabetically

It has two way to display list

- Without Sort Key (Array of Strings).
- With Sort Key (Array of Objects).

## Install

`npm install ngx-group-by-alphabates --save`

## Usage

| Param | Type |  Details |
| ------ | ------ | ------ | 
| input | array | array of string or object to group alphabetically.|
| sortKey | string | Sort key is required for input type array.|

**Events**
- onItemClick(element) - Click event for list item.
- onHeaderClick(header) - Click event of alphabet header.

Import `GroupByAlphabatesModule` module to your **app.module.ts**

```
import { NgModule } from '@angular/core';
import { BrowserModule  } from '@angular/platform-browser';
import { AppComponent } from './app';

import { GroupByAlphabatesModule } from 'ngx-group-by-alphabates';

@NgModule({
  imports: [BrowserModule, GroupByAlphabatesModule],
  declarations: [AppComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}
```
**Without Sort Key (Array of Strings)**
Input is array or string. For this type `sortKey` is not required.

**In HTML template**
```
<group-by-alphabates [input]="input" (itemClick)="obj = $event"></group-by-alphabates>
```

**In Compontent**
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  input = ["John", "Mary", "Mike", "Julie", "Adam"];
}
```
**With Sort Key (Array of Objects)**
Input is array or objects. For this type `sortKey` is required.

**In HTML template**
```
<group-by-alphabates [input]="input" [sortKey]="sortKey" (itemClick)="obj = $event"></group-by-alphabates>
```

**In Compontent**
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  input = [{"name": "John"}, {"name": "Mary"}, {"name": "Mike"}, {"name": "Julie"}, {"name": "Adam"}];
  sortKey = 'name';
}
```

## License
[MIT](https://tldrlegal.com/license/mit-license) © [Kaustubh Khare](https://github.com/kaustubhkhare19)
