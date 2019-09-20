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
