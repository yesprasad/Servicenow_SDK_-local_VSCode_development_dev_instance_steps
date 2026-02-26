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

![Screenshot 2026-02-26 at 1.19.30 PM.png](attachment:0ffe3954-fa4f-42d0-ab0c-96932f3f7d4e:Screenshot_2026-02-26_at_1.19.30_PM.png)

1. `mkdir my-fluent-app && cd my-fluent-app`
2. `npm install @servicenow/sdk`
3. now do `npx @servicenow/sdk init`
4. it shows a list of options for creating a project

![Screenshot 2026-02-26 at 1.23.13 PM.png](attachment:94f85b77-20ca-4f52-9feb-b4f5a4e57865:Screenshot_2026-02-26_at_1.23.13_PM.png)

1. Try selecting → now-sdk + basic

![Screenshot 2026-02-26 at 1.27.19 PM.png](attachment:af590c80-33ea-4e1f-94c1-5956e2c237be:Screenshot_2026-02-26_at_1.27.19_PM.png)

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
