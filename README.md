# Servicenow SDK set up for local VSCode development for Dev Instance

ServiceNow gives you a dev instance when you create one using the option at [developer.servicenow.com](http://developer.servicenow.com) 

1. goto [developer.servicenow.com](http://developer.servicenow.com) 
2. Login → Request an instance
3. wait for a few mintues to get it up and running. 
4. goto Manage instance and grab the instanceURL → something like → `https://dev220636.service-now.com/`
5. if you want you can reset the password after logging into the instance or grab the username: admin (default) and password.

As a Pro developer, once you create the instance, you have 2 options to start creating custom scoped applications - 

1. using the IDE option on the instance inside the web browser
2. using SDK in VSCode

In this document, I will walk you through how to setup the local VSCode development on MacOS which is pretty similar on Windows too. 

Once you have VSCode installed - 

1. then give the below command in the command line

`npx @servicenow/sdk auth save default \
--instance <your_instance_url_from_above_point_4> \
--user admin \
--password <your_instance_password_from_point_5>`

1. type `npx @servicenow/sdk auth —list` and it will show details something like below which means the authentication is set and ready to be used.

<img width="1574" height="304" alt="Screenshot_2026-02-26_at_1 19 30_PM" src="https://github.com/user-attachments/assets/8707003d-a8c5-45f4-9581-7309f0f9b664" />


1. `mkdir my-fluent-app && cd my-fluent-app`
2. `npm install @servicenow/sdk`
3. now do `npx @servicenow/sdk init`
4. it shows a list of options for creating a project

<img width="1752" height="584" alt="Screenshot_2026-02-26_at_1 23 13_PM" src="https://github.com/user-attachments/assets/623e7a40-c75d-4fb1-a4e7-d4f592d9122d" />


1. Try selecting → now-sdk + basic

<img width="2060" height="378" alt="Screenshot_2026-02-26_at_1 27 19_PM" src="https://github.com/user-attachments/assets/e6d581e4-c7d8-46b6-8fbd-aa774853dbf1" />


1. do `npm install`
2. it generates the below folder structure 

```jsx

└── 📁src
    └── 📁fluent
        ├── example.now.ts
        ├── index.now.ts
        ├── tsconfig.client.json
        ├── tsconfig.json
        ├── tsconfig.server.json
    └── 📁server
        ├── script.ts
        └── tsconfig.json

```

1. do `npm run build`  to build the project
2. do `npm run deploy` to build and deploy project your above instance
3. go back to the instance in browser and search for your app and you would now see it in the list of your custom apps.

Happy coding!
