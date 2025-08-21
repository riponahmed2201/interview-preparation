Got it 👍 You want **Laravel interview questions and answers (150–200+)** in markdown format, like we did for Node.js and TypeScript.
I’ll prepare a **comprehensive list** covering beginner, intermediate, and advanced topics.

Here’s the first big batch (about 60 Q\&A to start). If you want, I can continue until we reach 200+.

---

# Laravel Interview Questions & Answers

## Basics of Laravel

### 1. What is Laravel?

Laravel is an open-source PHP framework based on MVC (Model–View–Controller) architecture. It provides features like routing, authentication, ORM (Eloquent), migrations, and Blade templating to speed up web application development.

---

### 2. What are the main features of Laravel?

- Eloquent ORM
- Artisan CLI
- Blade Templating Engine
- Migration System
- Middleware
- RESTful Routing
- Authentication & Authorization
- Queues & Jobs
- Event Broadcasting
- Service Container

---

### 3. What is MVC in Laravel?

- **Model** → Handles database queries and logic.
- **View** → Manages presentation/UI (Blade templates).
- **Controller** → Connects Models & Views, contains business logic.

---

### 4. What is Composer in Laravel?

Composer is a PHP dependency manager. Laravel uses Composer to install and manage its packages/libraries.

---

### 5. What is Artisan in Laravel?

Artisan is Laravel’s command-line interface used for repetitive tasks like migrations, seeding, cache clearing, creating models/controllers, etc.
Example:

```bash
php artisan migrate
php artisan make:model Product -m
```

---

### 6. What is Eloquent ORM?

Eloquent is Laravel’s built-in ORM (Object-Relational Mapper). It provides an easy ActiveRecord-like syntax to interact with the database using models instead of raw SQL queries.

---

### 7. What is the default database engine in Laravel?

Laravel supports multiple databases (MySQL, PostgreSQL, SQLite, SQL Server). The default is usually **MySQL**.

---

### 8. What is a Service Provider in Laravel?

Service providers are the central place where all Laravel app bootstrapping occurs. They register bindings in the service container, event listeners, middleware, and route definitions.

---

### 9. What is Middleware in Laravel?

Middleware acts as a filter for HTTP requests entering the application. Examples include authentication, logging, and CSRF protection.
Example:

```php
Route::get('/profile', function () {
   // Only authenticated users
})->middleware('auth');
```

---

### 10. What are Laravel Facades?

Facades provide a static interface to classes in Laravel’s service container. Examples: `Cache::get()`, `DB::table()`, `Route::get()`.

---

## Routing & Requests

### 11. How do you define routes in Laravel?

Routes are defined in `routes/web.php` (for web) and `routes/api.php` (for APIs).
Example:

```php
Route::get('/users', [UserController::class, 'index']);
```

---

### 12. What are route groups in Laravel?

Route groups allow applying common attributes like middleware, prefixes, or namespaces.

```php
Route::prefix('admin')->middleware('auth')->group(function () {
    Route::get('/dashboard', [AdminController::class, 'dashboard']);
});
```

---

### 13. What is CSRF protection in Laravel?

Laravel protects against Cross-Site Request Forgery attacks using a CSRF token in forms:

```blade
<form method="POST">
   @csrf
</form>
```

---

### 14. How do you handle validation in Laravel?

Using `validate()` in controllers or Form Requests.

```php
$request->validate([
   'email' => 'required|email',
   'password' => 'required|min:6'
]);
```

---

### 15. How do you handle file uploads in Laravel?

```php
if ($request->hasFile('avatar')) {
   $path = $request->file('avatar')->store('avatars');
}
```

---

## Database & Eloquent

### 16. How do you create a migration in Laravel?

```bash
php artisan make:migration create_users_table
```

---

### 17. How do you run migrations?

```bash
php artisan migrate
```

---

### 18. How do you rollback migrations?

```bash
php artisan migrate:rollback
```

---

### 19. How do you define relationships in Eloquent?

- One-to-One

```php
return $this->hasOne(Profile::class);
```

- One-to-Many

```php
return $this->hasMany(Post::class);
```

- Many-to-Many

```php
return $this->belongsToMany(Role::class);
```

---

### 20. What are Accessors and Mutators in Laravel?

- **Accessor**: Format data when retrieving.

```php
public function getFullNameAttribute() {
    return ucfirst($this->first_name).' '.ucfirst($this->last_name);
}
```

- **Mutator**: Modify data before saving.

```php
public function setPasswordAttribute($value) {
    $this->attributes['password'] = bcrypt($value);
}
```

---

### 21. What is a Seeder in Laravel?

Seeders populate the database with test data.

```bash
php artisan make:seeder UserSeeder
```

---

### 22. How do you use factories in Laravel?

Factories generate fake data for testing/seeding.

```php
User::factory()->count(10)->create();
```

---

### 23. How do you use query builder in Laravel?

```php
$users = DB::table('users')->where('status', 'active')->get();
```

---

### 24. What is eager loading in Laravel?

Eager loading prevents N+1 query problem.

```php
$users = User::with('posts')->get();
```

---

### 25. What is lazy loading in Laravel?

Lazy loading loads relationships when accessed.

```php
$user = User::first();
$posts = $user->posts; // Query runs here
```

---

## Authentication & Security

### 26. How do you implement authentication in Laravel?

Using `php artisan make:auth` (in older versions) or Laravel Breeze, Jetstream, or Fortify in latest versions.

---

### 27. What is Sanctum in Laravel?

Sanctum provides a lightweight authentication system for SPAs, mobile apps, and APIs using API tokens.

---

### 28. What is Passport in Laravel?

Passport is an OAuth2 authentication system for APIs. It’s more powerful than Sanctum and supports authorization codes, clients, and scopes.

---

### 29. What is hashing in Laravel?

Laravel provides `Hash` facade for hashing passwords.

```php
Hash::make('password123');
```

---

### 30. What is encryption in Laravel?

Encryption secures data using AES-256-CBC by default.

```php
Crypt::encrypt('secret');
Crypt::decrypt($value);
```

---

## Advanced Laravel

### 31. What are Laravel Queues?

Queues allow background job processing (emails, notifications). Drivers include `database`, `redis`, `beanstalkd`.

---

### 32. What is Laravel Horizon?

Horizon is a dashboard for monitoring Laravel queues (only for Redis).

---

### 33. What is Laravel Telescope?

Telescope is a debugging assistant providing insights into requests, queries, jobs, and exceptions.

---

### 34. What are Events and Listeners in Laravel?

Events allow decoupled communication. Listeners respond to those events.

```bash
php artisan make:event OrderPlaced
php artisan make:listener SendOrderEmail
```

---

### 35. What are Laravel Policies?

Policies organize authorization logic.

```php
$this->authorize('update', $post);
```

---

### 36. What is the difference between Policies and Gates?

- **Gates** → Closure-based, for simple authorization.
- **Policies** → Class-based, tied to models, for structured authorization.

---

### 37. What are Laravel Jobs?

Jobs are queued tasks that run asynchronously. Example: sending emails.

---

### 38. What are Laravel Notifications?

Laravel provides notification channels like mail, database, SMS, and Slack.

---

### 39. What are Laravel Observers?

Observers listen to model events (created, updated, deleted).

---

### 40. What are Laravel Packages?

Reusable modules or libraries for Laravel apps. Example: `spatie/laravel-permission`.

---

### 41. How do you cache in Laravel?

```php
Cache::put('key', 'value', 600);
$value = Cache::get('key');
```

---

### 42. What are Laravel Contracts?

Contracts are interfaces that define core services. Example: `Illuminate\Contracts\Queue\Queue`.

---

### 43. What are Service Containers in Laravel?

Service Container is Laravel’s IoC (Inversion of Control) container that manages class dependencies and injections.

---

### 44. What is Dependency Injection in Laravel?

It’s a way to automatically resolve class dependencies via the service container.

---

### 45. What are Laravel Macros?

Macros extend existing classes with custom methods. Example: adding new methods to collections.

---

### 46. How do you schedule tasks in Laravel?

Using the `app/Console/Kernel.php`:

```php
$schedule->command('emails:send')->daily();
```

---

### 47. What is Laravel Scout?

Laravel Scout provides full-text search functionality using drivers like Algolia, Meilisearch.

---

### 48. What is Laravel Sail?

Sail is a Docker environment for Laravel apps.

---

### 49. What is Laravel Octane?

Octane boosts performance by serving apps using Swoole or RoadRunner.

---

### 50. What is the difference between `require` and `require_once` in PHP (in context of Laravel)?

- `require` loads file every time.
- `require_once` loads file only once to avoid redeclaration errors.

---

## Blade & Views

### 51. What is Blade in Laravel?

Blade is Laravel’s templating engine. It allows using template inheritance, sections, and directives like `@if`, `@foreach`.

---

### 52. How do you extend layouts in Blade?

```blade
@extends('layouts.app')

@section('content')
   <h1>Dashboard</h1>
@endsection
```

---

### 53. What are Blade components?

Reusable UI pieces. Example:

```blade
<x-alert type="success" message="Saved successfully!" />
```

---

### 54. What are Blade directives?

Special instructions in Blade like:

- `@if`, `@else`, `@endif`
- `@foreach`, `@endforeach`
- `@csrf`, `@method`

---

### 55. What is the difference between `{{ }}` and `{!! !!}` in Blade?

- `{{ $var }}` → Escaped output (prevents XSS).
- `{!! $var !!}` → Unescaped output (renders raw HTML).

---

### 56. How do you include another Blade file?

```blade
@include('partials.header')
```

---

### 57. What is the difference between `@include` and `@component` in Blade?

- `@include` → Simply includes a Blade file.
- `@component` → Uses Blade components with slots.

---

### 58. How do you pass data to a Blade view?

```php
return view('profile', ['user' => $user]);
```

---

### 59. How do you display old input values in Blade?

```blade
<input type="text" name="name" value="{{ old('name') }}">
```

---

### 60. How do you show validation errors in Blade?

```blade
@error('email')
   <span class="text-danger">{{ $message }}</span>
@enderror
```

---

## API Development

### 61. How do you create an API in Laravel?

Define routes in `routes/api.php` and use controllers.

```php
Route::get('/users', [UserController::class, 'index']);
```

---

### 62. What is API Resource in Laravel?

API Resources transform models into JSON-friendly format.

```php
return new UserResource($user);
```

---

### 63. How do you create API Resource?

```bash
php artisan make:resource UserResource
```

---

### 64. What is the difference between `api.php` and `web.php` routes?

- `web.php` → Has session, CSRF, cookies.
- `api.php` → Stateless, no sessions, best for REST APIs.

---

### 65. How do you version APIs in Laravel?

By prefixing routes:

```php
Route::prefix('v1')->group(function () {
    Route::get('/users', [UserController::class, 'index']);
});
```

---

### 66. What is the difference between `GET`, `POST`, `PUT`, and `DELETE` in Laravel routes?

- `GET` → Retrieve data
- `POST` → Create new data
- `PUT/PATCH` → Update data
- `DELETE` → Delete data

---

### 67. How do you use pagination in APIs?

```php
return User::paginate(10);
```

---

### 68. How do you send JSON response in Laravel?

```php
return response()->json(['status' => 'success']);
```

---

### 69. What is CORS in Laravel?

CORS (Cross-Origin Resource Sharing) controls which domains can access your API. Configured in `config/cors.php`.

---

### 70. How do you rate limit APIs in Laravel?

Using `throttle` middleware:

```php
Route::middleware('throttle:60,1')->group(function () {
    Route::get('/users', [UserController::class, 'index']);
});
```

---

## Testing

### 71. What testing tools does Laravel support?

Laravel supports **PHPUnit** and **Pest** for unit and feature testing.

---

### 72. How do you create a test in Laravel?

```bash
php artisan make:test UserTest
```

---

### 73. What is the difference between Feature and Unit tests in Laravel?

- **Unit Test** → Tests a single class/method.
- **Feature Test** → Tests an entire functionality (e.g., route + controller + DB).

---

### 74. How do you run tests in Laravel?

```bash
php artisan test
```

---

### 75. How do you mock a dependency in tests?

Using Laravel’s `Mockery` or `facade testing`. Example:

```php
Cache::shouldReceive('get')->once()->andReturn('value');
```

---

### 76. How do you test API endpoints?

```php
$response = $this->get('/api/users');
$response->assertStatus(200);
```

---

### 77. How do you test database with Laravel?

Use `RefreshDatabase` trait and factories.

---

### 78. How do you fake queues in Laravel tests?

```php
Queue::fake();
```

---

### 79. How do you test emails in Laravel?

```php
Mail::fake();
```

---

### 80. How do you test events in Laravel?

```php
Event::fake();
```

---

## Performance & Optimization

### 81. How do you improve Laravel performance?

- Use caching (config, routes, queries)
- Optimize Composer autoload
- Use queues for heavy tasks
- Use eager loading
- Use Octane (Swoole/RoadRunner)

---

### 82. How do you cache routes in Laravel?

```bash
php artisan route:cache
```

---

### 83. How do you cache config in Laravel?

```bash
php artisan config:cache
```

---

### 84. How do you cache views in Laravel?

```bash
php artisan view:cache
```

---

### 85. How do you clear all caches?

```bash
php artisan optimize:clear
```

---

### 86. What is Laravel Horizon used for performance?

Horizon is used for monitoring queues in real-time with a dashboard.

---

### 87. What are database indexing strategies in Laravel?

Using migrations:

```php
$table->index('email');
$table->unique('username');
```

---

### 88. How do you prevent N+1 problem in Laravel?

Using eager loading (`with()`).

---

### 89. What is database connection pooling?

Pooling allows reusing DB connections (done in Octane, not default Laravel).

---

### 90. How do you compress assets in Laravel?

Using **Laravel Mix/Vite** for minification & bundling.

---

## Deployment & DevOps

### 91. How do you deploy a Laravel app?

- Upload code
- Configure `.env`
- Run `composer install`
- Run migrations & seeders
- Cache routes/config/views
- Set correct permissions

---

### 92. What is Laravel Forge?

Forge is a deployment tool for provisioning & managing Laravel apps on cloud servers.

---

### 93. What is Laravel Envoyer?

Envoyer is a zero-downtime deployment tool for Laravel apps.

---

### 94. What is the `.env` file in Laravel?

`.env` stores environment-specific variables like DB credentials, API keys, app name.

---

### 95. What are queues in deployment context?

Queues run background jobs (emails, notifications) on workers.

---

### 96. How do you schedule cron jobs in Laravel?

```bash
* * * * * php /path/to/artisan schedule:run >> /dev/null 2>&1
```

---

### 97. How do you set file permissions for Laravel in Linux?

```bash
sudo chown -R www-data:www-data storage bootstrap/cache
```

---

### 98. What is the difference between `php artisan serve` and Apache/Nginx?

- `php artisan serve` → Development server.
- Apache/Nginx → Production server.

---

### 99. How do you use Docker with Laravel?

Use Laravel Sail (default Docker setup).

---

### 100. How do you use CI/CD with Laravel?

Using GitHub Actions, GitLab CI, or Jenkins to automate testing & deployment.

---

## Events, Broadcasting & Real-time

### 101. What is Laravel Broadcasting?

Broadcasting allows server-side events to be pushed to the client in real-time using WebSockets.

---

### 102. Which broadcasting drivers does Laravel support?

- Pusher
- Ably
- Redis
- Log
- Null

---

### 103. How do you create an event in Laravel?

```bash
php artisan make:event OrderPlaced
```

---

### 104. How do you create a listener in Laravel?

```bash
php artisan make:listener SendOrderNotification
```

---

### 105. How do you register events & listeners?

Inside `EventServiceProvider`.

---

### 106. How do you broadcast an event?

```php
broadcast(new OrderPlaced($order));
```

---

### 107. What is `ShouldBroadcast` in Laravel?

An interface that tells Laravel to broadcast the event to WebSockets.

---

### 108. What is Laravel Echo?

A JavaScript library that listens to broadcasted events from the server.

---

### 109. What is the difference between `broadcast()` and `event()` in Laravel?

- `event()` → Fires event within the app.
- `broadcast()` → Fires event and sends it to WebSockets for real-time clients.

---

### 110. What are private and presence channels in Laravel broadcasting?

- **Private channel** → For authenticated users.
- **Presence channel** → Tracks users currently subscribed.

---

## Advanced Database Concepts

### 111. How do you perform soft deletes in Laravel?

```php
use Illuminate\Database\Eloquent\SoftDeletes;

class Post extends Model {
    use SoftDeletes;
}
```

---

### 112. How do you restore soft deleted records?

```php
Post::withTrashed()->where('id', 1)->restore();
```

---

### 113. How do you force delete a soft-deleted record?

```php
$post->forceDelete();
```

---

### 114. What is the difference between `withTrashed()` and `onlyTrashed()`?

- `withTrashed()` → Fetches all including deleted.
- `onlyTrashed()` → Fetches only deleted.

---

### 115. How do you create database transactions in Laravel?

```php
DB::transaction(function () {
   // queries
});
```

---

### 116. How do you use raw SQL in Laravel?

```php
DB::select('SELECT * FROM users WHERE active = ?', [1]);
```

---

### 117. What is chunking in Laravel queries?

Fetching large datasets in smaller chunks.

```php
User::chunk(100, function ($users) {
   foreach ($users as $user) {
      // process
   }
});
```

---

### 118. What is cursor in Laravel queries?

A memory-efficient way to iterate records.

```php
foreach (User::cursor() as $user) {
    // process
}
```

---

### 119. How do you use DB transactions with rollback manually?

```php
DB::beginTransaction();
try {
   // queries
   DB::commit();
} catch (\Exception $e) {
   DB::rollback();
}
```

---

### 120. How do you implement multi-database connections in Laravel?

Define connections in `config/database.php`, then:

```php
User::on('mysql2')->get();
```

---

## Authentication & Authorization

### 121. What is the difference between Auth::attempt() and Auth::login()?

- `attempt()` → Tries to login with given credentials.
- `login()` → Logs in a given user instance.

---

### 122. How do you implement multi-auth in Laravel?

By defining multiple guards in `config/auth.php`.

---

### 123. What is the default guard in Laravel?

`web` (for sessions).

---

### 124. How do you restrict routes to authenticated users?

```php
Route::middleware('auth')->group(function () {
    Route::get('/dashboard', function () { ... });
});
```

---

### 125. How do you use roles & permissions in Laravel?

Using `spatie/laravel-permission` package.

---

### 126. How do you create a custom guard?

Define a new guard in `config/auth.php` and implement driver logic.

---

### 127. How do you log out a user?

```php
Auth::logout();
```

---

### 128. How do you get currently authenticated user?

```php
Auth::user();
```

---

### 129. What is password reset flow in Laravel?

Uses `Password::broker()` to send reset link → user resets password via token.

---

### 130. How do you throttle login attempts in Laravel?

Laravel provides `Illuminate\Foundation\Auth\ThrottlesLogins`. Middleware: `throttle:5,1`.

---

## Storage & File Handling

### 131. How do you store files in Laravel?

```php
$request->file('avatar')->store('avatars');
```

---

### 132. How do you store files with a custom disk?

```php
Storage::disk('s3')->put('file.jpg', $content);
```

---

### 133. What is the default filesystem in Laravel?

`local` (storage/app).

---

### 134. How do you create a symbolic link for storage?

```bash
php artisan storage:link
```

---

### 135. How do you download a file in Laravel?

```php
return response()->download(storage_path('app/file.pdf'));
```

---

### 136. How do you delete a file in Laravel?

```php
Storage::delete('avatars/file.jpg');
```

---

### 137. How do you get URL of a file stored in S3?

```php
Storage::disk('s3')->url('file.jpg');
```

---

### 138. How do you check if a file exists in Laravel storage?

```php
Storage::exists('avatars/file.jpg');
```

---

### 139. How do you serve private files in Laravel?

Using signed URLs:

```php
URL::temporarySignedRoute('download', now()->addMinutes(5), ['file' => 'report.pdf']);
```

---

### 140. How do you upload multiple files in Laravel?

```php
foreach ($request->file('photos') as $photo) {
    $photo->store('photos');
}
```

---

## Laravel Testing (Advanced)

### 141. How do you use database migrations in tests?

Using `RefreshDatabase` trait:

```php
use RefreshDatabase;
```

---

### 142. How do you test authentication in Laravel?

```php
$this->actingAs(User::factory()->create())
     ->get('/dashboard')
     ->assertStatus(200);
```

---

### 143. How do you fake notifications in Laravel tests?

```php
Notification::fake();
```

---

### 144. How do you test API rate limiting?

```php
$response = $this->get('/api/users');
$response->assertStatus(429);
```

---

### 145. How do you test middleware?

Attach middleware in test route and check response.

---

### 146. How do you use `assertDatabaseHas()` in tests?

```php
$this->assertDatabaseHas('users', ['email' => 'test@example.com']);
```

---

### 147. How do you use `assertDatabaseMissing()` in tests?

```php
$this->assertDatabaseMissing('users', ['email' => 'fake@example.com']);
```

---

### 148. How do you test queued jobs?

```php
Bus::fake();
```

---

### 149. How do you use factories with relationships in tests?

```php
User::factory()->hasPosts(3)->create();
```

---

### 150. How do you test file uploads in Laravel?

```php
Storage::fake('avatars');
$file = UploadedFile::fake()->image('avatar.jpg');
```

---

## Laravel Packages & Ecosystem

### 151. What is Spatie Laravel Permission?

A package to handle roles and permissions in Laravel applications.

---

### 152. How do you install Spatie Permission?

```bash
composer require spatie/laravel-permission
```

---

### 153. What is Laravel Socialite?

A package for OAuth authentication with providers like Google, Facebook, GitHub, LinkedIn.

---

### 154. How do you install Laravel Socialite?

```bash
composer require laravel/socialite
```

---

### 155. What is Laravel Cashier?

A package for handling subscription billing with Stripe & Paddle.

---

### 156. What is Laravel Jetstream?

An application starter kit providing authentication, registration, email verification, 2FA, team management.

---

### 157. What is Laravel Breeze?

A lightweight authentication starter kit using Blade or Inertia.

---

### 158. What is Laravel Fortify?

A backend implementation of Laravel’s authentication features (login, registration, 2FA, password reset).

---

### 159. What is Laravel Nova?

A premium admin panel for Laravel apps.

---

### 160. What is Laravel Spark?

A subscription billing system with built-in SaaS boilerplate.

---

## Laravel Jobs & Queues

### 161. What is the difference between sync and async queue drivers?

- **sync** → Executes immediately.
- **async** → Runs in the background (Redis, Beanstalkd).

---

### 162. How do you create a job in Laravel?

```bash
php artisan make:job SendEmailJob
```

---

### 163. How do you dispatch a job?

```php
SendEmailJob::dispatch($user);
```

---

### 164. How do you run queue workers?

```bash
php artisan queue:work
```

---

### 165. What is the difference between `queue:work` and `queue:listen`?

- `queue:work` → Long-running process.
- `queue:listen` → Restarts for every job (slower).

---

### 166. How do you delay a job in Laravel?

```php
SendEmailJob::dispatch($user)->delay(now()->addMinutes(10));
```

---

### 167. How do you retry failed jobs?

```bash
php artisan queue:retry all
```

---

### 168. How do you monitor jobs in Laravel?

Using **Laravel Horizon** for Redis queues.

---

### 169. How do you configure queue retries?

In `config/queue.php` under `retry_after`.

---

### 170. How do you store failed jobs?

By configuring `failed` table via migration:

```bash
php artisan queue:failed-table
php artisan migrate
```

---

## Laravel Advanced Concepts

### 171. What is Laravel Macros?

A way to add custom methods to classes like Collections or Response.

---

### 172. What is Laravel Mix (before Vite)?

A wrapper around Webpack for asset compilation (CSS/JS).

---

### 173. What is Laravel Vite?

Default frontend build tool since Laravel 9 for bundling assets.

---

### 174. What is Laravel Telescope?

A debugging assistant showing requests, queries, jobs, exceptions.

---

### 175. What is Laravel Octane?

Improves performance using Swoole or RoadRunner servers.

---

### 176. What is Inertia.js in Laravel?

A library to build single-page apps without APIs using Vue/React + Laravel.

---

### 177. What is Livewire in Laravel?

A full-stack framework for dynamic UI without writing JavaScript.

---

### 178. What is the difference between Livewire and Inertia?

- **Livewire** → Blade + dynamic interactions (no JS).
- **Inertia** → Vue/React + Laravel (SPA approach).

---

### 179. What are Laravel Policies?

Classes that handle authorization for models.

---

### 180. What are Laravel Gates?

Closures used for simple authorization logic.

---

## Laravel Testing (More Advanced)

### 181. How do you test email content in Laravel?

```php
Mail::assertSent(WelcomeMail::class, function ($mail) {
    return $mail->hasTo('test@example.com');
});
```

---

### 182. How do you test jobs are dispatched?

```php
Bus::assertDispatched(SendEmailJob::class);
```

---

### 183. How do you test file downloads?

```php
$response = $this->get('/download');
$response->assertDownload('report.pdf');
```

---

### 184. How do you use HTTP tests in Laravel?

```php
$this->get('/users')->assertStatus(200);
```

---

### 185. How do you test routes with middleware?

```php
$this->withoutMiddleware()->get('/dashboard');
```

---

### 186. How do you test validation errors?

```php
$this->post('/register', [])->assertSessionHasErrors('email');
```

---

### 187. How do you use `assertSee` in tests?

```php
$this->get('/home')->assertSee('Welcome');
```

---

### 188. How do you test authentication?

```php
$this->actingAs(User::factory()->create())->get('/dashboard')->assertOk();
```

---

### 189. How do you test JSON responses?

```php
$this->getJson('/api/users')->assertJson(['status' => 'success']);
```

---

### 190. How do you run specific tests?

```bash
php artisan test --filter=UserTest
```

---

## Laravel Security

### 191. How do you prevent SQL injection in Laravel?

Using Eloquent/Query Builder parameter binding.

---

### 192. How do you prevent XSS in Laravel?

Use `{{ $var }}` (escaped output).

---

### 193. How do you prevent CSRF in Laravel?

Laravel adds `_token` with `@csrf` in forms.

---

### 194. How do you encrypt sensitive data?

```php
Crypt::encrypt('secret');
```

---

### 195. How do you use signed URLs in Laravel?

```php
URL::signedRoute('unsubscribe', ['user' => 1]);
```

---

### 196. How do you enable HTTPS in Laravel?

Set `APP_URL=https://example.com` and force HTTPS in middleware.

---

### 197. How do you prevent mass assignment in Laravel?

Using `$fillable` or `$guarded` in models.

---

### 198. What is Laravel Rate Limiting?

A feature to throttle API requests using `throttle` middleware.

---

### 199. What is Laravel CSRF Middleware?

A middleware that checks request tokens for form submissions.

---

### 200. What are the best practices for securing Laravel apps?

- Use environment variables for secrets.
- Use HTTPS.
- Sanitize inputs.
- Use Laravel’s validation rules.
- Apply CSRF, XSS, and SQL injection protections.
- Limit API requests.
- Keep packages updated.

---
