GoMobileDetect
==============

[![GoDoc](https://godoc.org/github.com/Shaked/gomobiledetect?status.png)](https://godoc.org/github.com/Shaked/gomobiledetect)
[![Build Status](https://travis-ci.org/Shaked/gomobiledetect.png?branch=master)](https://travis-ci.org/Shaked/gomobiledetect)
[![Coverage Status](https://coveralls.io/repos/Shaked/gomobiledetect/badge.png)](https://coveralls.io/r/Shaked/gomobiledetect)

### Description

GoMobileDetect is a lightweight package imported from PHP for detecting mobile devices including tablets. 

The package is imported from [MobileDetect](http://www.mobiledetect.net) which was originally written in PHP.

### Compare Benchmarking

#### original version
```
BenchmarkIsMobile-4        100000         23107 ns/op
BenchmarkIs-4              100000         15073 ns/op
BenchmarkIsKey-4           100000         15475 ns/op
BenchmarkVersion-4         100000         16322 ns/op
BenchmarkVersionKey-4      100000         16444 ns/op
```

#### this package with stored/multimap in safe mode
```
BenchmarkIsMobile-4        500000          3078 ns/op
BenchmarkIs-4             1000000          1227 ns/op
BenchmarkIsKey-4          1000000          1069 ns/op
BenchmarkVersion-4         100000         16325 ns/op
BenchmarkVersionKey-4      100000         15928 ns/op
```

#### this package with stored/multimap in unsafe mode
```
BenchmarkIsMobile-4        200000          7948 ns/op
BenchmarkIs-4              500000          4039 ns/op
BenchmarkIsKey-4           500000          3840 ns/op
BenchmarkVersion-4         100000         16260 ns/op
BenchmarkVersionKey-4      100000         16517 ns/op
```

### Installation 

    $ go get github.com/Shaked/gomobiledetect 

### Updates 

#### Version 1.2.0 

- Now supports using ```Http.Handler``` implementation. See [examples](https://github.com/Shaked/gomobiledetect/tree/master/examples) 

#### Version 1.0.0
- The package name had been changed to *mobiledetect*. 
 
#### Version 0.2.0
- This version introduces a new method ```IsKey(key int)```. This method is faster than the ```Is(key string)```. All keys can be found [here](https://github.com/Shaked/gomobiledetect/blob/maps-to-lists/rules.go#L4)

- The ```Is(key string)``` has been changed to support both ```string``` and ```int``` using the ```interface{}```. 

#### Benchmarking 

##### Version 0.1.2
```
BenchmarkIsMobile       2000       1001884 ns/op
ok      github.com/Shaked/gomobiledetect    7.091s
```

##### Version 0.2.0
```
BenchmarkIsMobile     100000         19278 ns/op
ok      github.com/Shaked/gomobiledetect    7.448s
```

### Usage

There are different ways of using the package: 

- [Basic usage](examples/app.go) 
- [Basic router implementation](examples/router.go)
- [Handler interface implementation](examples/app_handler.go)
- [Mux interface implementation](examples/app_mux.go)

### License

Go Mobile Detect is an open-source script released under [MIT License](http://www.opensource.org/licenses/mit-license.php). 