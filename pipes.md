## Pipes
    Pipes are a feature built into Angular 2 that allows you transform output in your template. 

    The main purpose of a pipe is to transform some output. Thier are different types of pipes for different types of output and also for synchronous and asynchronous data. 

     A pipe can be used to transform the way text is displayed on the output, example all caps.

     {{ username | uppercase }}

     There are several built in pipes available to use with Angular. As well as being able to build your own to use.

## Built in Pipes
    Go to Angular.io under docs then click on the API Reference and then it will dispaly the latest version at the top. You can ignore that just type 'pipe' into the search. This will list all the pipes that can be used in Angular. This also shows the examples that can be used as well. Great Information!! 

## Chaning Multiple pipes together

    So in order to use multiple pipes together you just add another | after the one you just used. Example:

    {{ server.started | date: 'fullDate' | uppercase }} 

    They are read from left to right... the order matters.

## Creating a custom pipe

    First you must create a file 
    ('shorten.pipe.ts')
      then inside that you will:

import { PipeTransform } from "@angular/core";

export class ShortenPipe implements PipeTransform{
  transform(value: any) {
    return value.substr(0, 10);
  }
}

    After this you will need to go to app.module.ts :

Add 'ShortenPipe' to the declarations and then make sure it is imported as well. 

    Then go back to the shorten.pipe.ts to add... @Pipe and make sure it imports above. so above the export class it will look like this:

@Pipe({
  name: 'shorten'
})

    In order to use this... now go to the html file and add:

             | shorten 

    where you want to display the custom pipe. However if it doesnt look the greatest.. lets work it.

    Go back to the shorten.pipe.ts and add:

              + '...' ; 

    after the return value.substr(0, 10)..

  Now when it displays only the first 10 characters it shows the ... so you know it has more information to pull.
