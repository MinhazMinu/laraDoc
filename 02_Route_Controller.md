## 02 Laravel Tutorials - Laravel Route, View and Controller in a depth

1. **Route with callback function.**

```
Route::get('/', function () {
    return view('welcome');
});
```

-   **with parameter**

```
Route::get('/{id}', function ($id) {
    return view('welcome');
});
```

2. **Route with controller class**

```
Route::get('/', [ControllerClass::method, 'function'])->name('routeName');

Route::get('/', [UsersControllers::class, 'index'])->name('user.index');
```

-   **with parameter & optional patameter**

```
Route::get('/{id}/{slug}', [UsersControllers::class, 'index'])->name('user.index');

Route::get('/{id}/{slug?}', [UsersControllers::class, 'index'])->name('user.index');
```

3. **Controller function for CRUD operation**

    - C -> Create page (create), Create form(store)
    - R -> Show list(index), Show single item(show)
    - U -> Edit page(edit), Update form(update)
    - D ->Delete list(destroy)

4. **View without controller**

```
Route::view('/','welcome');
```

5. **Route group with prefix & name**

```
Route::prefix('users')->name('users')->group(function(){
    Route::get('/',UsersController::class,'index')->name('index');
    Route::get('/create',UsersController::class,'create')->name('create');
})
```

6. **Route redirect**

```
Route::redirect('/','/dashboard');
```
7. **Resource route**
```
Route::resource('users',UsersControllers::class);

==============
To check Route
php artisan r:l
```
