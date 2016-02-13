# angular2-log

This package provide an easy to use log system for angular2 applications.

Every log are outputted to a named logger.
Each logger has an Observable that can be subscribed in order to achieve various interesting stuffs !

I hope this will help !

## Usage

Install it:
```
npm install --save angular2-log
```

Update System.js config.
This is needed to map import of angular2-log to the right folder.  
*( I do not really get why it's needed, so if anybody have a clue or an answer, please
let me know !)*
```
System.config({
    map: {
        'angular2-log': 'node_modules/angular2-log'
    },
    packages: {
        'angular2-log': {
            defaultExtension: 'js'
        },
        'public/js': {
            format: 'register',
            defaultExtension: 'js'
        }
    }
});
```


Add to your injector the provider for the log service:
```javascript
import {LogService} from 'angular2-log/log';

// To add the provider at your root injector
bootstrap(DemoComponent, [LogService]);
```

Inject the service where needed, and use it !

```javascript
export class YourComponent {
    constructor(public logService: LogService) {
		this.logService.debug('Your debug stuff');
		this.logService.info('An info');
		this.logService.warning('Take care ');
		this.logService.error('Too late !');
    }
}
```


## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

* 0.0.2: Still working on it :)

## Contact

* Web: [http://clement-vidal.fr](http://clement-vidal.fr)
* Twitter: [clementvidal_](https://twitter.com/clementvidal_)
* Mail: clementvidalperso(at)gmail(dot)com

## License

* [MIT](https://opensource.org/licenses/MIT)
