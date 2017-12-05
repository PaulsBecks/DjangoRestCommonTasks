# Ajax

## Submit form with Ajax

``` js

$('#form').submit(function(){
    $.ajax({
      url: $('#form').attr('action'),
      type: 'POST',
      data : $('#form').serialize(),
      error: function (xhr, ajaxOptions, thrownError) {
        alert(xhr.status); //alerts the error code 
      }
    });
    return false;
});

```
