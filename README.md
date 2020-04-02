# firebaseLoader
Manage firebase in javascript
- [x] auto imports firebase modules
- [x] database integration
-------------------------------------------------
WARNING: error not supported in min.js version
-------------------------------------------------
##instructions
- constructor(config: firebaseConfigJson, callback: funtion)
- constructor(config: firebaseConfigJson, callback: funtion, imp: array)
- getModError(): int
- getModLoaded(): int
- getDatabase(): firebase
- getModuleStats(): boolean
- getCallback(): function
- getImportFiles(): array
- getValuesDatabase(callback: function): void
- getValueKeyDatabase(key: String, callback: function): void
- writeDatabase(key: String, values: json)
- importAllModule(): void //imports modules from firebase
- importModule(url: String): void //import one specific module
```js
/*
  Example write and read database from firebase
*/
var firebaseConfig = {
    apiKey: "",
    authDomain: "",
    databaseURL: "",
    projectId: "",
    storageBucket: "",
    messagingSenderId: "",
    appId: "",
    measurementId: ""
};
var g = new firebaseLoader(firebaseConfig, function(e){

    /*
      Get values from database
    */
    e.getValuesDatabase(function(key,val){
        console.log(key,val);
    });
    
    
    
    /*
      Write on the database
    */
    e.writeDatabase("animes",{val: "Hey"});
    
    
});

/*
  Imports module of firebase and launch the function above
  WARNING: obligatory function to launch the script !
*/
g.importAllModule();
```
