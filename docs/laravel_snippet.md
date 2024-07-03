# Laravel snippet

## Route

Pass an array of variable to the view
```php
<?php
Route::get('/jobs', function () {
    return view('jobs', [
        'jobs' => [
            [
                'id' => 1,
                'title' => 'Director',
                'salary' => '$50,000'
            ],
            [
                'id' => 2,
                'title' => 'Programmer',
                'salary' => '$10,000'
            ],
        ]
    ]);
});
```

## Eager load

Load all the jobs with their related employers.  
Limit the number of sql request, by loading all the employer.
Otherwise a new query would be executed when accessing info on the employer (lazy loading).

```php
<?php
$jobs = Job::with('employer')->get();
```
>Note: lazy loading can be disabled

## Display form validation error (blade)

Use the `@error` directive, with the id/name of the input.

```html
<input id='last-name' name='last-name' >

@error('last-name')
<p class="text-xs text-red-500 font-semibold">
  {{ $message }}
</p>
@enderror
```
