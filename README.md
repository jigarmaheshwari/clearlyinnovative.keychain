# Appcelerator  clearlyinnovative.keychain #

INSTALL YOUR MODULE
--------------------

1. Run `build.py` which creates your distribution
2. cd to `/Library/Application Support/Titanium`
3. copy this zip file into the folder of your Titanium SDK

REGISTER YOUR MODULE
---------------------

Register your module with your application by editing `tiapp.xml` and adding your module.
Example:

		<modules>
			<module version="0.1">clearlyinnovative.keychain</module>
		</modules>

When you run your project, the compiler will know automatically compile in your module
dependencies and copy appropriate image assets into the application.

USING YOUR MODULE IN CODE
-------------------------

To use your module in code, you will need to require it. 

For example,

		var keychain = require('clearlyinnovative.keychain');

		keychain.setForKey({
			key: "name",
			value: "asaunders-two",
			serviceName: "MYAPPID"
		},
		function(data) {
			Ti.API.info(JSON.stringify(data));
		});

		keychain.getForKey({
			key: "name",
			serviceName: "MYAPPID"
		},
		function(data) {
			Ti.API.info(JSON.stringify(data));
		});


		// removeForKey
		keychain.removeForKey({
			key: "name",
			serviceName: "MYAPPID"
		},
		function(data) {
			Ti.API.info(JSON.stringify(data));
		});

		// SHOULD ERROR SINCE WE REMOVED KEY
		keychain.getForKey({
			key: "name",
			serviceName: "MYAPPID"
		},
		function(data) {
			Ti.API.info(JSON.stringify(data));
		});



## RELEASE NOTES ##

Enjoy -if you have questions or issues, please post here

based on code from the iPhone Developer's Cookbook

## LICENSE ##

SFHFKeychainUtils code by:
  Created by Buzz Andersen on 10/20/08.
  Based partly on code by Jonathan Wight, Jon Crosby, and Mike Malone.
  Copyright 2008 Sci-Fi Hi-Fi. All rights reserved.


The MIT License

Copyright (c) 2012 Aaron Saunders

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
