# NEST JS

## Initial Project without nest CLI client:

```cmd
npm init -y
```

```cmd
npm install @nestjs/common @nestjs/core @nestjs/platform-express reflect-metadata typescript 
```

```cmd
npm install class-validator class-transformer
```
## Typescript config:
```cmd
// tsconig.json
{
	"compilerOptions": {
		"module": "commonjs",
		"target": "es2017",
		"experimentalDecorators": true,
		"emitDecoratorMetadat": true
	}
}
```

## Nest Tools : 

### Pipe: 
- Validate data contained in the request. OR Validates incoming data.

### Guard: 
- Make sure the user is authenticated. OR Handles Authentication.

### Controller: 
- Route the request to a particular function. OR handles incoming request.

### Service:
- Run some business login. OR Handles data access and business logic.

### Repository: 
- Handles data stored in DB. OR Handles data stored in DB.

### Interceptor: 
- Adds extra logic to **incoming requests** or **outgoing responses**.

### Filters:
- Handles Error that occur during request handling.

### Modules:
- Groups together Code.

## File Naming Convention:
- One class per file (Some exception).
- Class name should include the kind of thing we are creating.
- Name of class and name of file should always match up.
- Filename Template : **name.type_of_thing.ts**

## Small Demo:

```javascript
// app.controller.ts
import {Controller, Get} from '@nestjs/common';

@Controller('/app')
export class AppController {
	@Get()
	getRootRoute() {
		return "HI";
	}
	@Get('/bye')
	getRootRoute() {
		return "BYE";
	}
}
```

```javascript
//app.module.ts
import {Module} from "@nestjs/common";
import {AppController} from "./app.controller";

@Module({
	controllers: [AppController]
	
})
export class AppModule { }
```

```javascript
// main.ts
import {NestFactory} from "@nestjs/core";
import {AppModule} from "./app.module";

async function bootstrap() {
	const app = await NestFactory.create(AppModule);
	app.listen(3000);
}
bootstrap();
```

```cmd
npx ts-node-dev main.ts
```

## NEST CLI:

### Install Globally : 
```cmd
sudo npm install -g @nestjs/cli
```

### Create new Project:
```cmd
nest new <project_name> OR <directory>(.)
```

### Creating Module:
```cmd
nest generate module <module_name>
```
- This command makes a new directory with module_name. And a message.module.ts is created in it.

### Creating Controller:
```cmd
nest generate controller <module_name>/<controller_name> --flat
```
- option `--flat` doesn't create an extra folder called `controller`
- most of the time, controller_name and module_name are the same.

## Adding Routing Logic:

```javascript
// messages.controller.ts

import {Controller, Get, Param, Body, Post} from '@nestjs/common';

@Controller('messages')
export class MessagesController {
	@Get()
	listMessages(){}

	@Post()
	createMessage(@Body() body:any){}

	@Get('/:id')
	getMessage(@Params('id') id: string){}
}
```

## Using ValidationPipe for validate incoming request: 
### One Time Step : Tell Nest to use global Validation
```javascript
// main.ts
import {ValidationPipe} from '@nestjs/common';

app.useGlobalPipes(
	new ValidationPipe({ whilelist: true })
);
```

***NOTE***:  
- we want to apply ValidationPipe to all incoming request but it doesn't mean we need to add validation rules to each and every route handler.
- `whitelist` property ensures that **only Dto provided properties**.

### Step 1: Create a class(Data Transfer Object) that describes the different properties that the request body should have. 

```javascript
// dtos/create-message.dto.ts
export class CreateMessageDto {
	content: string;
}
```

### Step 2: Add validation rules to the class

```javascript
// dtos/create-message.dto.ts
import {IsString} from 'class-validator';
export class CreateMessageDto {
	@IsString()
	content: string;
}
```

### Step 3: Apply that class to the request handler

```javascript
// messages.controller.ts
import {Controller, Get, Param, Body, Post} from '@nestjs/common';
import {CreateMessageDto} from './dtos/create-message.dto';

@Controller('messages')
export class MessagesController {
	@Get()
	listMessages(){}

	@Post()
	createMessage(@Body() body:CreateMessageDto){}

	@Get('/:id')
	getMessage(@Params('id') id: string){}
}
```
