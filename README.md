# lognext

The logger nobody asked for


# Installation

```shell
npm install lognext
```

# Usage

## Getting Started

Require the module and instantiate an instance. The topic name is used when tracing messages to help identify their source.

```JavaScript
const Lognext = require('lognext');
const log = new Lognext('topic-name');
```

## Learn by example!

Standard stuff

```JavaScript
log.writeBox('Standard trace messages');

log.error('This is an error');
log.warn('You have been warned');
log.info('This is informational');
log.verbose('This message is really a lot more information than you probably wanted');
log.debug('This message is for debugging');
log.silly('Tee hee hee!');
```

![img](https://raw.githubusercontent.com/PrinceNebulon/lognext/master/images/standard-trace-messages.png)


Objects can be traced out too!

```JavaScript
log.writeBox('Tracing with objects');

log.error(new Error('This is an error'));
let data = { prop1: 'val1', prop2: ['a', 'b', 'c']};
log.info('Data: ', data);
log.debug('Data: ', data);
```

![img](https://raw.githubusercontent.com/PrinceNebulon/lognext/master/images/tracing-with-objects.png)


Color can be turned off for output windows that don't support ANSI colors.

```JavaScript
log.setUseColor(false);
log.error('This is an error');
log.warn('You have been warned');
log.info('This is informational');
log.verbose('This message is really a lot more information than you probably wanted');
log.debug('This message is for debugging');
log.silly('Tee hee hee!');
```

![img](https://raw.githubusercontent.com/PrinceNebulon/lognext/master/images/no-color.png)


Trace levels can be controlled to disable traces above the set level.

```JavaScript
log.writeBox('Log Level Examples');
['error', 'warn', 'info', 'verbose', 'debug', 'silly'].forEach((level) => {
	console.log(`+++ Log level => ${level}`);
	log.setLogLevel(level);
	log.error('This is an error');
	log.warn('You have been warned');
	log.info('This is informational');
	log.verbose('This message is really a lot more information than you probably wanted');
	log.debug('This message is for debugging');
	log.silly('Tee hee hee!');
});
```

![img](https://raw.githubusercontent.com/PrinceNebulon/lognext/master/images/log-levels.png)


Profile a string to measure time!

```JavaScript
log.profile('foo');
log.writeBox('Let\'s profile!');
setTimeout(()=>{log.profile('foo');}, 100);
```

![img](https://raw.githubusercontent.com/PrinceNebulon/lognext/master/images/profiling.png)
