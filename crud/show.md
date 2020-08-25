# Show Config

## Introduction

In the `show` method of a **Form** or a **CRUD** config all components and
fields are configured for editing the data. The first parameter is an instance
of `Ignite\Page\Page` so all functions described in the
[Page](../basics/page.md) documentation can be used.

```php
use Ignite\Crud\CrudShow;

public function show(CrudShow $page)
{
    // Define the page here.
}
```

## Card

Form fields must be grouped into `cards`. You are free to create only one or any
number of cards for a form.

```php
use Ignite\Crud\CrudShow;

public function show(CrudShow $page)
{
    $page->card(function ($form) {

        // Build your form in here.

        $form->input('first_name')->title('First Name');

    })
    ->title('Card Title')
    ->width(8);
}
```

All available fields can be found in the documentation under
[Fields](../fields/introduction.md).

## Group

With `group` fields can be grouped in a column. This is useful to organize form
elements of different heights side by side.

```php
$form->group(function($form) {
    // Build your form inside the col.
})->width(6);
```

Read the [Extend Vue](../basics/vue.md#bootstrap-vue) section to learn how to
register your own Vue components.

## Info

A good content administration interface includes **descriptions** that help the
user to quickly understand what is happening on the interface. Such information
can be created outside and inside of cards like this:

```php
use Ignite\Crud\CrudShow;

public function show(CrudShow $page)
{
    $page->info('Address')
        ->width(4)
        ->text('This address appears on your <a href="'.route('invoices').'">invoices</a>.')
        ->text(...);

    // ...
}
```

## Preview

It is possible to get a `preview` of the stored data directly in the update
form. The **route** for this can be easily specified using the method
`previewRoute`. For a CRUD Model, the corresponding model is also passed as a
parameter.

```php
public function previewRoute($article)
{
    return route('article', $article->id);
}
```

Now the page can be previewed for the devices **desktop**, **tablet** or
**mobile**.

### Default Device

The default device can be changed in the config `lit.php` under
'crud.preview.default_device'.

```php
'crud' => [
    'preview' => [
        // Available devices: mobile, tablet, desktop
        'default_device' => 'desktop'
    ]
],
```
