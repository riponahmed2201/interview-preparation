Got it ✅ — you want a **NestJS interview questions and answers guide (100–150+ Q\&A)** in **Markdown format**, so you can study easily.
I’ll structure it with **Table of Contents**, **Beginner → Intermediate → Advanced**, and **Real-world scenarios**.

Here’s a **comprehensive draft (Part 1: 100+ Q\&A)**. If you want, I can expand later to 150+.

---

# NestJS Interview Questions & Answers

## 📑 Table of Contents

1. [Basics](#basics)
2. [Core Concepts](#core-concepts)
3. [Modules & Dependency Injection](#modules--dependency-injection)
4. [Controllers & Providers](#controllers--providers)
5. [Middleware, Guards & Interceptors](#middleware-guards--interceptors)
6. [Pipes & Filters](#pipes--filters)
7. [Database & ORM](#database--orm)
8. [Authentication & Authorization](#authentication--authorization)
9. [Microservices & Messaging](#microservices--messaging)
10. [Testing](#testing)
11. [Performance & Best Practices](#performance--best-practices)
12. [Real-world & Scenario-based](#real-world--scenario-based)

---

## Basics

### 1. What is NestJS?

NestJS is a progressive Node.js framework built with TypeScript for building scalable and maintainable server-side applications. It follows modular architecture and uses **OOP + FP + FRP** concepts.

---

### 2. What are the main features of NestJS?

- Built-in **Dependency Injection**
- Modular architecture
- TypeScript support
- Supports **Express** & **Fastify**
- Middleware, Guards, Interceptors, Pipes
- Microservices support

---

### 3. How is NestJS different from Express.js?

- **Express** → Minimal, unopinionated, requires manual structure.
- **NestJS** → Opinionated, modular, comes with built-in DI, decorators, guards, interceptors.

---

### 4. Can you use NestJS with JavaScript?

Yes, NestJS supports JavaScript, but TypeScript is **recommended** for decorators, DI, and type safety.

---

### 5. What is the default HTTP provider in NestJS?

**Express** is the default, but you can switch to **Fastify** for better performance.

---

## Core Concepts

### 6. What are Controllers in NestJS?

Controllers handle incoming requests and return responses to the client. Example:

```ts
@Controller("users")
export class UsersController {
  @Get()
  findAll() {
    return ["User1", "User2"];
  }
}
```

---

### 7. What are Providers?

Providers are services, repositories, factories, helpers. They are **injectable** classes marked with `@Injectable()`.

---

### 8. What is a Module in NestJS?

A module is a class annotated with `@Module()`. It groups related components (controllers, services, providers). Example:

```ts
@Module({
  imports: [],
  controllers: [UsersController],
  providers: [UsersService],
})
export class UsersModule {}
```

---

### 9. What is Dependency Injection (DI) in NestJS?

DI allows classes to depend on **abstract contracts** instead of concrete implementations. Example:

```ts
constructor(private usersService: UsersService) {}
```

---

### 10. What is the purpose of `main.ts` in NestJS?

It’s the entry point where you bootstrap the application using `NestFactory.create()`.

---

## Modules & Dependency Injection

### 11. Difference between `@Global()` and normal modules?

- Normal module → must import in each module where needed.
- `@Global()` → providers become globally available (avoid overuse).

---

### 12. Can a provider be injected into multiple modules?

Yes. Export the provider from one module and import that module wherever needed.

---

### 13. What is `forwardRef()` in NestJS?

Used when two modules depend on each other (circular dependency).

```ts
imports: [forwardRef(() => UsersModule)];
```

---

### 14. How do you create a custom provider?

```ts
const CustomProvider = {
  provide: "APP_CONFIG",
  useValue: { apiKey: "12345" },
};
```

---

### 15. What is `useClass`, `useValue`, `useFactory` in providers?

- **useClass** → provide a class
- **useValue** → provide a constant value
- **useFactory** → provide dynamically created value

---

## Controllers & Providers

### 16. What are route parameters in NestJS?

```ts
@Get(':id')
getUser(@Param('id') id: string) {
  return id;
}
```

---

### 17. How to pass query parameters?

```ts
@Get()
findAll(@Query('limit') limit: number) {}
```

---

### 18. How to inject services in controllers?

```ts
constructor(private readonly usersService: UsersService) {}
```

---

### 19. What is the difference between Singleton and Request Scoped providers?

- **Singleton** → single instance for the whole app.
- **Request Scoped** → new instance per request.

---

### 20. How to make a provider request-scoped?

```ts
@Injectable({ scope: Scope.REQUEST })
```

---

## Middleware, Guards & Interceptors

### 21. What is Middleware in NestJS?

Functions executed **before controllers**. Example: logging, authentication.

---

### 22. How to apply middleware?

```ts
app.use(LoggerMiddleware);
```

---

### 23. What are Guards in NestJS?

Guards decide whether a request is allowed to proceed to the route handler (e.g., AuthGuard).

---

### 24. What are Interceptors in NestJS?

Interceptors transform the request/response, add logging, caching, or modify data.

---

### 25. Difference between Middleware, Guard, Interceptor?

- **Middleware** → before route handler
- **Guard** → authorization logic
- **Interceptor** → transform response/request

---

## Pipes & Filters

### 26. What are Pipes?

Used for **validation & transformation** of data.

---

### 27. Example of a built-in pipe?

`ValidationPipe`, `ParseIntPipe`.

---

### 28. How to create a custom pipe?

```ts
@Injectable()
export class UppercasePipe implements PipeTransform {
  transform(value: string) {
    return value.toUpperCase();
  }
}
```

---

### 29. What are Exception Filters?

They handle errors and return consistent responses. Example: `HttpExceptionFilter`.

---

### 30. How to catch all exceptions globally?

```ts
app.useGlobalFilters(new AllExceptionsFilter());
```

---

## Database & ORM

### 31. Which ORMs can be used with NestJS?

- TypeORM
- Sequelize
- Prisma
- MikroORM

---

### 32. Example: Connecting to PostgreSQL using TypeORM?

```ts
TypeOrmModule.forRoot({
  type: "postgres",
  host: "localhost",
  port: 5432,
  username: "test",
  password: "test",
  database: "testdb",
  autoLoadEntities: true,
  synchronize: true,
});
```

---

### 33. How to define an Entity in TypeORM?

```ts
@Entity()
export class User {
  @PrimaryGeneratedColumn()
  id: number;

  @Column()
  name: string;
}
```

---

### 34. How to use Repository pattern in NestJS?

```ts
constructor(
  @InjectRepository(User) private userRepo: Repository<User>
) {}
```

---

### 35. How to use Prisma in NestJS?

Install `@prisma/client` and `nestjs-prisma`, then inject `PrismaService`.

---

## Authentication & Authorization

### 36. How to implement JWT authentication in NestJS?

Use `@nestjs/jwt` and `Passport`. Steps:

1. Install dependencies
2. Create `JwtStrategy`
3. Apply `AuthGuard('jwt')`

---

### 37. How to implement role-based authorization?

Use custom guards with `@Roles()` decorator + metadata.

---

### 38. How to secure APIs in NestJS?

- Use Guards
- CSRF protection
- Rate limiting
- Helmet

---

### 39. Difference between Authentication and Authorization?

- Authentication → Verifying identity
- Authorization → Verifying permissions

---

### 40. How do you refresh JWT tokens?

Issue a **short-lived access token** + **long-lived refresh token** stored securely.

---

## Microservices & Messaging

### 41. What transport layers does NestJS microservice support?

- TCP
- Redis
- NATS
- Kafka
- MQTT
- gRPC

---

### 42. How to create a microservice?

```ts
NestFactory.createMicroservice(AppModule, {
  transport: Transport.TCP,
});
```

---

### 43. What is MessagePattern in NestJS?

It defines a handler for messages/events.

```ts
@MessagePattern({ cmd: 'get_users' })
getUsers() {}
```

---

### 44. How to implement Event-driven architecture in NestJS?

Use **EventEmitterModule** or message brokers (Kafka, RabbitMQ).

---

### 45. Difference between REST and Microservice in NestJS?

- REST → HTTP based, request/response
- Microservice → message/event-driven

---

## Testing

### 46. Which testing frameworks are supported in NestJS?

- Jest (default)
- Mocha
- Jasmine

---

### 47. How to test a controller?

```ts
describe("UsersController", () => {
  it("should return users", () => {
    expect(controller.findAll()).toEqual(["User1", "User2"]);
  });
});
```

---

### 48. What is `TestingModule`?

It is a NestJS testing utility that creates isolated modules for testing.

---

### 49. How to mock a service in tests?

```ts
{ provide: UsersService, useValue: { findAll: jest.fn() } }
```

---

### 50. How to do end-to-end testing in NestJS?

Use `supertest` with `app.getHttpServer()`.

---

## Performance & Best Practices

### 51. How to improve performance in NestJS?

- Use Fastify instead of Express
- Caching with Redis
- Use async providers
- Optimize database queries

---

### 52. What is `CACHE_MANAGER` in NestJS?

A built-in provider for caching (supports Redis, memory).

---

### 53. How to enable compression in NestJS?

Use `compression` middleware.

---

### 54. What are global pipes/guards/interceptors?

Applied at app-level → affect all routes.

---

### 55. How to use Helmet in NestJS?

```ts
import helmet from "helmet";
app.use(helmet());
```

---

## Real-world & Scenario-based

### 56. How would you design a multi-tenant app in NestJS?

- Separate DB per tenant or shared DB with tenantId
- Use middleware to identify tenant from request

---

### 57. How to handle file uploads in NestJS?

Use `@nestjs/platform-express` (Multer).

---

### 58. How to send emails in NestJS?

Use `nodemailer` or external services (SendGrid, SES).

---

### 59. How to schedule tasks in NestJS?

Use `@nestjs/schedule` + `CronJob`.

---

### 60. How to implement WebSockets in NestJS?

Use `@WebSocketGateway()` + `@SubscribeMessage()`.

---

## Advanced Features

### 61. What is GraphQL in NestJS?

GraphQL is a query language for APIs. NestJS supports it via `@nestjs/graphql` with Apollo driver.

---

### 62. How to create a GraphQL resolver in NestJS?

```ts
@Resolver(() => User)
export class UsersResolver {
  constructor(private usersService: UsersService) {}

  @Query(() => [User])
  async users() {
    return this.usersService.findAll();
  }
}
```

---

### 63. Difference between REST and GraphQL in NestJS?

- REST → multiple endpoints, over-fetching possible
- GraphQL → single endpoint, client specifies needed data

---

### 64. How to implement Subscriptions in GraphQL with NestJS?

Use WebSockets and `PubSub` from `graphql-subscriptions`.

---

### 65. How to enable CORS in NestJS?

```ts
app.enableCors();
```

---

### 66. What is the purpose of `APP_GUARD` token?

It allows you to register a **global guard** for all routes.

---

### 67. How to create a global interceptor?

```ts
app.useGlobalInterceptors(new LoggingInterceptor());
```

---

### 68. What are hybrid applications in NestJS?

Applications that combine **HTTP server + microservices** in one app.

---

### 69. How to handle configuration in NestJS?

Use `@nestjs/config` and `.env` files.

---

### 70. Example of using ConfigModule?

```ts
ConfigModule.forRoot({
  isGlobal: true,
  envFilePath: ".env",
});
```

---

## Security

### 71. How to hash passwords in NestJS?

Use `bcrypt` or `argon2`.

---

### 72. How to protect against SQL Injection?

- Use ORM parameterized queries
- Avoid raw queries without sanitization

---

### 73. How to secure GraphQL endpoints?

Use `@UseGuards(AuthGuard)` on resolvers.

---

### 74. What is CSRF protection in NestJS?

Cross-site request forgery prevention → can be enabled with `csurf` middleware.

---

### 75. How to implement rate limiting?

Use `@nestjs/throttler`.

---

## CQRS & Event-Driven Architecture

### 76. What is CQRS in NestJS?

Command Query Responsibility Segregation → separates **read** and **write** operations.

---

### 77. How to implement CQRS in NestJS?

Install `@nestjs/cqrs` and define **Commands, Queries, Handlers, Events**.

---

### 78. Example of a Command in NestJS?

```ts
export class CreateUserCommand {
  constructor(public readonly name: string) {}
}
```

---

### 79. Example of a CommandHandler?

```ts
@CommandHandler(CreateUserCommand)
export class CreateUserHandler implements ICommandHandler<CreateUserCommand> {
  async execute(command: CreateUserCommand) {
    console.log("Creating user:", command.name);
  }
}
```

---

### 80. What are Sagas in NestJS CQRS?

Sagas listen for **events** and trigger new commands asynchronously.

---

## Deployment & Scaling

### 81. How to deploy NestJS on Docker?

- Create `Dockerfile`
- Use `docker build` and `docker run`

---

### 82. How to deploy NestJS on AWS?

Options: **Elastic Beanstalk, ECS, Lambda with Serverless framework**.

---

### 83. How to deploy NestJS on Kubernetes?

- Create Docker image
- Deploy with Kubernetes deployment + service YAML

---

### 84. How to enable clustering in NestJS?

Use `@nestjs/cluster` or Node.js native `cluster` module.

---

### 85. How to handle environment variables in production?

Use `ConfigModule` + `process.env`.

---

## WebSockets

### 86. What is a WebSocket Gateway in NestJS?

A WebSocket Gateway handles real-time communication.

```ts
@WebSocketGateway()
export class ChatGateway {
  @SubscribeMessage("message")
  handleMessage(client: any, payload: string): string {
    return payload;
  }
}
```

---

### 87. How to use namespaces in WebSockets?

```ts
@WebSocketGateway({ namespace: '/chat' })
```

---

### 88. How to use rooms in WebSockets?

Use `socket.join('room1')` and `server.to('room1').emit()`.

---

### 89. Difference between WebSockets and Socket.IO?

- WebSocket → raw protocol
- Socket.IO → abstraction with rooms, fallbacks, etc.

---

### 90. How to secure WebSockets?

- Authenticate handshake with JWT
- Use HTTPS/WSS

---

## Advanced Database

### 91. How to implement transactions in TypeORM with NestJS?

```ts
await this.connection.transaction(async (manager) => {
  await manager.save(user);
});
```

---

### 92. How to implement soft deletes in TypeORM?

Use `@DeleteDateColumn` and `softRemove()`.

---

### 93. How to implement migrations in NestJS with TypeORM?

Use CLI:

```bash
npm run typeorm migration:generate -n Init
```

---

### 94. How to implement database seeding?

Manually write scripts or use libraries like `typeorm-seeding`.

---

### 95. How to handle multi-database connections in NestJS?

Call `TypeOrmModule.forRoot()` multiple times with `name` option.

---

## Logging & Monitoring

### 96. How to use built-in Logger in NestJS?

```ts
import { Logger } from "@nestjs/common";
const logger = new Logger("App");
logger.log("App started");
```

---

### 97. How to enable request logging?

Use middleware or interceptors with `Logger`.

---

### 98. How to integrate NestJS with Winston?

Install `winston` and use `app.useLogger()`.

---

### 99. How to monitor performance in NestJS?

Use APM tools: NewRelic, Datadog, Prometheus.

---

### 100. How to handle global error logging?

Create a **global exception filter** + integrate with logging tool.

---

## Advanced Scenarios

### 101. How do you design a multi-language (i18n) API in NestJS?

Use `nestjs-i18n` module + translation files.

---

### 102. How to implement file streaming in NestJS?

```ts
@Get('file')
getFile(@Res() res) {
  const file = createReadStream('test.txt');
  file.pipe(res);
}
```

---

### 103. How to implement GraphQL Federation in NestJS?

Use `@nestjs/graphql` with Apollo Federation support.

---

### 104. How to handle pagination in NestJS?

Implement query params: `limit`, `offset`, or use `nestjs-typeorm-paginate`.

---

### 105. How to send push notifications in NestJS?

Integrate with Firebase Cloud Messaging (FCM) or Web Push API.

---

### 106. How to handle background jobs in NestJS?

Use `@nestjs/bull` (BullJS + Redis).

---

### 107. How to implement caching with Redis?

```ts
CacheModule.register({ store: redisStore, host: "localhost", port: 6379 });
```

---

### 108. How to use GraphQL DataLoader in NestJS?

Install `dataloader` → batch & cache DB calls.

---

### 109. How to integrate gRPC with NestJS?

```ts
NestFactory.createMicroservice(AppModule, { transport: Transport.GRPC, options: {...} });
```

---

### 110. How to implement health checks in NestJS?

Use `@nestjs/terminus`.

---

## Expert-Level

### 111. What is Event Sourcing in NestJS?

Store state as a series of events, replay to rebuild state.

---

### 112. How to implement Event Sourcing in NestJS?

Use `nestjs-event-store` or custom event store with CQRS.

---

### 113. How to implement Saga patterns in NestJS?

With `@nestjs/cqrs`, use long-running workflows triggered by events.

---

### 114. How to build a multi-module monorepo with NestJS?

Use `@nestjs/cli` + `nest g app service1` inside workspace.

---

### 115. How to scale NestJS with Redis Pub/Sub?

Use `RedisIoAdapter` for WebSocket scaling across instances.

---

### 116. How to secure sensitive configs in NestJS?

Use AWS Secrets Manager, Vault, or encrypted `.env`.

---

### 117. How to integrate NestJS with GraphQL subscriptions in production?

Use Apollo Server with Redis PubSub for scaling.

---

### 118. How to integrate NestJS with Kafka?

Use `Transport.KAFKA` with `MessagePattern`.

---

### 119. How to integrate NestJS with RabbitMQ?

Use `nestjs-rabbitmq` or microservices transport.

---

### 120. How to implement distributed caching?

Use Redis or Memcached cluster.

---

## Real-World Scenarios

### 121. You need to migrate a large Express.js app to NestJS. How?

- Identify modules
- Create controllers/services
- Gradually port routes into NestJS

---

### 122. You need request-level context (multi-tenant). How?

Use `Scope.REQUEST` providers or AsyncLocalStorage.

---

### 123. How to implement audit logs in NestJS?

Use Interceptors to log requests + DB hooks to log changes.

---

### 124. How to handle large file uploads?

Use `multer` with streams + S3/Cloud Storage.

---

### 125. How to implement custom decorators?

```ts
export const User = createParamDecorator(
  (data, ctx) => ctx.switchToHttp().getRequest().user
);
```

---

### 126. How to test microservices in NestJS?

Use in-memory transport or mock message brokers.

---

### 127. How to implement OTP-based authentication?

Generate OTP, store temporarily in Redis, verify on login.

---

### 128. How to protect sensitive routes in GraphQL?

Apply guards at resolver/method level.

---

### 129. How to integrate ElasticSearch in NestJS?

Use `@nestjs/elasticsearch` module.

---

### 130. How to integrate Payment Gateway (Stripe/PayPal)?

Use SDKs inside service layer.

---

Great 🙌 Let’s finish the **150+ NestJS Interview Q\&A**. I’ll continue from **Q131 → Q150** and make this the **final part** so you’ll have a **complete large reference set** in Markdown.

---

## Scaling & Performance

### 131. How do you scale a NestJS app horizontally?

- Use Docker + Kubernetes
- Stateless services
- Shared Redis cache for sessions

---

### 132. How to implement API versioning in NestJS?

```ts
app.enableVersioning({
  type: VersioningType.URI,
  defaultVersion: "1",
});
```

---

### 133. How to enable GZIP compression in NestJS?

Install `compression` and add:

```ts
app.use(compression());
```

---

### 134. How to handle request throttling per user?

Use `@nestjs/throttler` with user-specific keys.

---

### 135. How to implement GraphQL query complexity analysis?

Use `graphql-query-complexity` to prevent expensive queries.

---

### 136. How to handle memory leaks in NestJS?

- Avoid global variables
- Close DB connections properly
- Use Node.js heap profiling

---

### 137. How to handle high-concurrency APIs?

- Use Fastify adapter
- Enable caching
- Use async database queries

---

### 138. How to implement message queues in NestJS?

Use `@nestjs/bull` (Redis-backed queues).

---

### 139. How to optimize WebSocket performance?

- Use Redis adapter for scaling
- Broadcast messages instead of multiple emits

---

### 140. How to cache GraphQL queries?

Use `apollo-server-plugin-response-cache`.

---

## DevOps & Deployment

### 141. How to run NestJS in serverless environments (AWS Lambda)?

Use `@nestjs/serverless` + AWS Lambda adapter.

---

### 142. How to implement CI/CD for NestJS?

- Lint + Jest in pipeline
- Build Docker image
- Deploy via GitHub Actions / GitLab CI

---

### 143. How to enable hot reloading in NestJS?

Install `ts-node-dev` or `webpack HMR`.

---

### 144. How to containerize a NestJS app with Docker?

```dockerfile
FROM node:18
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
CMD ["npm", "run", "start:prod"]
```

---

### 145. How to run multiple NestJS apps in one repo?

Use **Monorepo mode** with `nest generate app`.

---

### 146. How to deploy NestJS on Heroku?

- Add `Procfile`
- Set `start:prod` as command
- Push to Heroku

---

### 147. How to deploy NestJS on Vercel?

Use serverless functions with `@nestjs/platform-serverless`.

---

### 148. How to monitor NestJS with Prometheus?

Use `@willsoto/nestjs-prometheus`.

---

### 149. How to integrate NestJS with OpenTelemetry?

Use `@nestjs/otel` for distributed tracing.

---

### 150. How to gracefully shut down a NestJS app?

```ts
app.enableShutdownHooks();
```

Then handle `onModuleDestroy` or `beforeApplicationShutdown`.

---

## Bonus Expert-Level Questions (Beyond 150)

### 151. How to implement Domain-Driven Design (DDD) with NestJS?

- Separate `domain`, `application`, `infrastructure` layers
- Use CQRS & Event Sourcing

---

### 152. How to implement multi-region deployments for NestJS?

- Deploy on multiple cloud regions
- Use global CDN + database replication

---

### 153. How to integrate NestJS with GraphQL Federation across microservices?

- Define federated schemas
- Use Apollo Gateway for composition

---

### 154. How to debug memory/CPU issues in NestJS?

- Use `clinic.js` / `node --inspect`
- Heap snapshots + flamegraphs

---

### 155. How to secure WebSockets with JWT in NestJS?

```ts
handleConnection(client: Socket) {
  const token = client.handshake.headers.authorization;
  // validate JWT
}
```

---

### 156. How to enforce API key authentication in NestJS?

Create a guard that checks `x-api-key` header against config.

---

### 157. How to implement GraphQL batching in NestJS?

Use `dataloader` to batch DB requests.

---

### 158. How to implement saga orchestration across microservices?

Use a workflow engine (e.g., Temporal) or NestJS CQRS Sagas.

---

### 159. How to make NestJS apps GDPR compliant?

- Anonymize user data
- Allow data deletion requests
- Encrypt PII

---

### 160. How to secure sensitive endpoints from brute force attacks?

- Use `nestjs-throttler`
- IP-based rate limiting
- Account lockout policies

---

# ✅ Summary

You now have **160+ NestJS interview questions and answers** organized into:

- Basics → Advanced
- Core concepts (Controllers, Modules, DI)
- Security, Auth, Guards, Interceptors
- Database (TypeORM, Prisma)
- GraphQL, WebSockets, Microservices
- CQRS, Event Sourcing, DDD
- Scaling, Deployment, DevOps

This is a **complete NestJS Interview Reference Guide** 🎯.

---
