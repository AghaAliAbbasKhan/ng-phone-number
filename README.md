# ng-phone-number
A simple international telephone number input. Allows you to create a phone number field with country dropdown. 

This is re-written version (with enhancement) of [ng4-intl-phone](https://github.com/kondi0/ng4-intl-phone/). So credit should go to [kondi0](https://github.com/kondi0) and nikhiln 
It just resolves an issue of +39 with itlay and vatican city as the code for vc is +379, all things remain the same with ngx-international-phone-number. Moreover i have added language support. Now we can access different languages using locale.
This library is created by [Agha Ali Abbas](https://github.com/AghaAliAbbasKhan).

## Installation

To install this library, run:

```bash
$ npm install ng-phone-number --save
```

## Consuming your library

Once you have installed it you can import `InternationalPhoneNumberModule` from `ng-phone-number` in any application module. E.g.

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your library
import { InternationalPhoneNumberModule } from 'ng-phone-number';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,

    // InternationalPhoneNumberModule module
    InternationalPhoneNumberModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Once it is imported, you can use `international-phone-number`:

```xml
<!-- app.component.html -->
<form name="sample-form" (ngSubmit)="submit()" #f="ngForm">
 <international-phone-number [(ngModel)]="model.phone_number" placeholder="Enter phone number" [maxlength]="20" [defaultCountry]="'in'" [locale]="'es'" [required]="true" #phoneNumber="ngModel" name="phone_number" [allowedCountries]="['in', 'ca', 'us']"></international-phone-number>

  <div *ngIf="f.submitted && !phoneNumber.valid" class="help-block">Phone number is required and should be valid</div>
  <button type="submit">Submit</button>
</form>
```

### Attributes/Options:
       defaultCountryCode : An ISO 639-1 country code can be provided to set default country selected.
       placeholder: A placeholder text which would be displayed in input widget
       required: Indicates whether it's required or not
       allowDropdown: Indicates whether to allow selecting country from dropdown
       allowedCountries: A list of countries (iso codes) that would get display in country dropdown. E.g. [allowedCountries]="['in', 'ca', 'us']" would only show Canada, India and US. If not provided, all the countries would get displayed.
       locale: It is for language support. If locale is not provided then english will be used by default.

## Troubleshooting:
If you are getting error "Can't resolve 'google-libphonenumber'" while building with aot, try to install google-libphonenumber. Run npm install google-libphonenumber@3.0.9 --save

## Supported Languages:
Right now ng-phone-number supports 2 languages.
1. English
2. Espanol

I am working on adding more languages,If you want your language to be added you can put up a request at
`aghaali.abbas@outlook.com`. You can also suggest any other feature.

## Authors
    * Original Author: kondi0
    * Author: Agha Ali Abbas
## License

MIT
