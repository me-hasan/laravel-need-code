# Ajax
```php
Route::POST('/getAllSegment/team', 'TeamController@getAllSegment')->name('get.all.segment');
```
```php
$(document).on('change', '#process', function()
{
    var id = $(this).val();
    $.ajax({
        url: "{{ route('get.all.segment') }}",
        type: 'POST',
        data: {"_token": "{{ csrf_token() }}","id": id},
        success: function(data) {
         console.log(data);
      }
    });
});
```

```php
public function getAllSegment(Request $request)
{
    dd($request->input('id'));
}
```

# Eloquent Relation
1. One to One :
             hasOne


2. Inverse One to One : 
            belongsTo


3. One to Many :
             hasMany


4. Many to Many (By PIVOT) :
            belongsToMany


5. Has Many Through : (Join Three table)
            hasManyThrough


6. Polymorphic Relation 
   main model === morphTo
   accessible model = morphMany   
