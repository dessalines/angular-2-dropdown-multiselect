# Angular 2 Dropdown Multiselect for Bootstrap CSS

Updated to work with RC6 !

Customizable dropdown multiselect in Angular 2, TypeScript with bootstrap css.

See demo: http://softsimon.github.io/angular-2-dropdown-multiselect

## Dependencies
* Bootstrap CSS 3
* Font Awesome

## Usage

Import `MultiselectDropdownModule` into your @NgModule.

```js
import { IMultiSelectOption } from 'multiselect-dropdown';

export class MyClass {
    private myOptions: IMultiSelectOption[] = [
        { id: 1, name: 'Option 1' },
        { id: 2, name: 'Option 2' },
    ];
}
```

In your template, use the component directive:

```html
<ss-multiselect-dropdown [options]="myOptions" [(ngModel)]="selectedOptions" (ngModelChange)="onChange($event)"></ss-multiselect-dropdown>
```

## Customize

Import the IMultiSelectSettings and IMultiSelectTexts interfaces to enable/override settings and text strings:
```js
private defaultSelected: Array<number> = [1, 2];

private mySettings: IMultiSelectSettings = {
    pullRight: false,
    enableSearch: false,
    checkedStyle: 'checkboxes',
    buttonClasses: 'btn btn-default',
    selectionLimit: 0,
    closeOnSelect: false,
    showCheckAll: false,
    showUncheckAll: false,
    dynamicTitleMaxItems: 3,
    maxHeight: '300px',
};

private myTexts: IMultiSelectTexts = {
    checkAll: 'Check all',
    uncheckAll: 'Uncheck all',
    checked: 'checked',
    checkedPlural: 'checked',
    searchPlaceholder: 'Search...',
    defaultTitle: 'Select',
};
```

```html
<ss-multiselect-dropdown [options]="mySettings" [texts]="myTexts" [settings]="mySettings" [(ngModel)]="selectedOptions"></ss-multiselect-dropdown>
```

## Developing

Pull requests are welcome!

## License

[MIT]