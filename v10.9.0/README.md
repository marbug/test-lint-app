# Test lint > v10.9.0 #

## Create project ##

        ng new marbug-app

* See changes [here](https://github.com/marbug/test-lint/compare/master...v10.9.0_step-1_create-project)

* Please, run

        npm run lint

    and see no error

## Go to project folder ##

        cd marbug-app

## Generate home module ##

        ng g module home

* See changes [here](https://github.com/marbug/test-lint/compare/v10.9.0_step-1_create-project...v10.9.0_step-2_generate-home-module)

* Please, run

        npm run lint

    and see no error

## Generate home component ##

        ng g component home

* See changes [here](https://github.com/marbug/test-lint/compare/v10.9.0_step-2_generate-home-module...v10.9.0_step-3_generate-home-component)

* Please, run

        npm run lint

    and see no error

## Change prefix ##

* Edit **marbug-app/angular.json** file and change prefix from **app** to **marbug**:

              "root": "",
              "sourceRoot": "src",
              "projectType": "application",
        -     "prefix": "app",
        +     "prefix": "marbug",
              "schematics": {},
              "architect": {
                "build": {

* See changes [here](https://github.com/marbug/test-lint/compare/v10.9.0_step-3_generate-home-component...v10.9.0_step-4_change-prefix)

* Please, check for lint errors

        npm run lint

    and see no error

## Change component selector prefix ##

* Edit **marbug-app/src/app/home/home.component.ts** file and change component selector prefix from **app** to **marbug**:

                @Component({
        -         selector: 'app-home',
        +         selector: 'marbug-home',
                  templateUrl: './home.component.html',
                  styleUrls: ['./home.component.css']
                })

* See changes [here](https://github.com/marbug/test-lint/compare/v10.9.0_step-4_change-prefix...v10.9.0_step-5_change-component-selector-prefix)

* Please, check for lint errors

        npm run lint

    and see error

        ERROR: /Users/marbug/cpp/angular/test-lint/marbug-app/src/app/home/home.component.ts[4, 13]: The selector of the component "HomeComponent" should have prefix "app" (https://angular.io/styleguide#style-02-07)

        Lint errors found in the listed files.

## Add component-selector rule ##

* Edit **marbug-app/tslint.json** file and add **component-selector** rule:

             "no-output-rename": true,
             "use-life-cycle-interface": true,
             "use-pipe-transform-interface": true,
        +    "component-selector": [true, "element", "marbug", "kebab-case"],
             "component-class-suffix": true,
             "directive-class-suffix": true
           }

* See changes [here](https://github.com/marbug/test-lint/compare/v10.9.0_step-5_change-component-selector-prefix...v10.9.0_step-6_add-component-selector-rule)

* Please, check for lint errors

        npm run lint

    and see error

        ERROR: /Users/marbug/cpp/angular/test-lint/marbug-app/src/app/home/home.component.ts[4, 13]: The selector of the component "HomeComponent" should have prefix "app" (https://angular.io/styleguide#style-02-07)

        Lint errors found in the listed files.

## Fix lint errors ##

* Remove **component-selector** rule from **marbug-app/tslint.json** file and fix prefix in **marbug-app/src/tslint.json** rule:

* See changes [here](https://github.com/marbug/test-lint/compare/v10.9.0_step-6_add-component-selector-rule...v10.9.0_step-7_fix-rules)

| Navigation |
| ---------- |
| [Up](../README.md) |
