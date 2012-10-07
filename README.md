# epubValidator - Check your EPUB Books

This library will check that your .epub files are valid IDPF EPUB v2.x documents and return a successful or error message. It can be called as a Ruby library, or invoked from the command line.

For more about the IDPF see http://idpf.org

For more about the epubcheck tool see http://code.google.com/p/epubcheck/


## Setup

```
gem install epub_validator
```

## Basic Usage

Sample usage and output:

``` ruby
require 'epub_validator'

ev = EpubValidator.check('/path/to/sample.epub')
puts ev[:valid]
ev[:message].each do |m|
  puts m
end
=> 0
=> ERROR: OPS/toc.ncx(21): 'OPS/': referenced resource exists, but not declared in the OPF file
```

Now from the command line:

``` terminal
$ epub_validator /path/to/sample.epub

Checking....FAILED!

ERROR: OPS/toc.ncx(21): 'OPS/': referenced resource exists, but not declared in the OPF file
```


## Requirements

Java must be installed and set in your PATH.

## Future Features

* Command line: accept directory containing many .epub files for processing.
* Command line: have switch for writing results to log file
* Format "ERROR" and "WARNING" output for more intuitive instructions.
