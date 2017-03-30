https://angular.io/docs/ts/latest/cookbook/form-validation.html

Tamplate Driven Forms
=====================

You can use HTML validation attributes like `pattern`, `min`, `max`, `required`, `step` or `maxlength`

More about them here: https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Constraint_validation

Example for a validated input:
```html
<label for="name">Name</label>

<input type="text" id="name" class="form-control"
       required minlength="4" maxlength="24"
       name="name" [(ngModel)]="hero.name"
       #name="ngModel" >

<div *ngIf="name.errors && (name.dirty || name.touched)"
     class="alert alert-danger">
    <div [hidden]="!name.errors.required">
      Name is required
    </div>
    <div [hidden]="!name.errors.minlength">
      Name must be at least 4 characters long.
    </div>
    <div [hidden]="!name.errors.maxlength">
      Name cannot be more than 24 characters long.
    </div>
</div>
```
