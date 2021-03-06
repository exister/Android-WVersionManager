Android-WVersionManager
====================

## Objective
Save time to implement check new update available since Google play havent provide any API to check (written at Jan 2013)

## Features
- Show Alert Dialog with new update content and 3 options button: update now, remind me later and ignore this version.
- Few lines of code to implement.

## Screenshots
![Screenshot](https://github.com/winsontan520/Android-WVersionManager/raw/master/screenshot1.png)

## Usage
1. Copy https://github.com/winsontan520/Android-WVersionManager/blob/master/wversionmanager-1.0.jar to your project libs folder. You may also check out src used as project library.
2. In your Activity, 

    	protected void onCreate(Bundle savedInstanceState) {
    		super.onCreate(savedInstanceState);
    		setContentView(R.layout.activity_main);
    		
    		WVersionManager versionManager = new WVersionManager(this);
    		versionManager.setVersionContentUrl("http://bit.ly/11c7Pnb"); // your update content url, see the response format below
    		versionManager.checkVersion();
    	}

3. The Version Content Url must return response with json format which follow this format. To save time for testing you may just put content in static text file.

		{
		"version_code": 2,
		"content": "Version 2.0 <p>New features:</p><li>Added feature A</li><li>Added feature B</li><li>Added feature C</li><li>Added feature D</li><li>Added feature E</li><li>Added feature F</li><li>Added feature G</li>"
		}

4. You can also customize label and reminder time eg:

    	versionManager.setUpdateNowLabel("Custom update now label");
    	versionManager.setRemindMeLaterLabel("Custom remind me later label");
    	versionManager.setIgnoreThisVersionLabel("Custom ignore this version");
    	versionManager.setUpdateUrl("http://your_app_url"); // this is the link will execute when update now clicked. default will go to google play based on your package name.
    	versionManager.setReminderTimer(10); // this mean checkVersion() will not take effect within 10 minutes

## License - Free to use
    Copyright 2013 Winson Tan
    
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
       http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
