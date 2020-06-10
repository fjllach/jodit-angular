> This is a fork of the main project "Jodit-Angular"

# Jodit Angular Component

This package is a wrapper around [Jodit](https://xdsoft.net/jodit/) to make it easier to use in a Angular application.

## for contributors
The editor component itselt is located in the `jodit-angular` folder and packaged into a redistributable package with the [ng-packagr](https://www.npmjs.com/package/ng-packagr) tool. A test app has been created with the @angular/cli. It is located in the src directory and a dev server can be started by using the `npm start` command.

## Installation
```bash
$ npm install jodit-angular
```

## Usage

### Loading the component

Import the EditorModule from the npm package like this:

```typescript
import { JoditAngularModule } from 'jodit-angular';
```

And add it to you application module:
```typescript
// This might look different depending on how you have set up your app
// but the important part is the imports array
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    JoditAngularModule // <- Important part
  ],
  providers: [],
  bootstrap: [AppComponent]
})
```

Using the component in your templates
Use the editor in your templates like this:

```html
<jodit-editor [config]="{buttons: 'bold'}"></jodit-editor>
```               

In config you can set all [Jodit's options](https://xdsoft.net/jodit/play.html)

**Note about toolbar buttons override:**

Jodit editor apply a different toolbar buttons layout based on width available for the editor itself.
So a different width size for editor will show a different buttons layout.
The "buttons" config setting in the example above will override only the default toolbar buttons for large widths.
If you want to override buttons displayed on all editor sizes use something like this:

```
<jodit-editor
  [config]="{
      buttons: 'bold,strikethrough,underline,italic'
      buttonsMD: 'bold,strikethrough,underline,italic'
      buttonsSM: 'bold,strikethrough,underline,italic'
      buttonsXS: 'bold,strikethrough,underline,italic'
      };"
></jodit-editor>     
```      

## Event binding
You can also bind editor events via a shorthand prop on the editor, for example:

```html
<jodit-editor (onChange)="handleEvent($event)"></jodit-editor>
```

### Events list

* onChange
* onKeydown
* onMousedown
* onClick
* onFocus
* onPaste
* onResize
* onBeforeEnter
* onBeforeCommand
* onAfterCommand
* onAfterExec
* onAfterPaste
* onChangeSelection

Where the handler gets called with an object containing the properties event, which is the event object, and editor, which is a reference to the editor.


\
License
-----
This package is available under `MIT` License.
