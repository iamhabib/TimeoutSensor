# TimeoutSensor
Timeout Sensor for Android Applications

This library will make it easy to set a session timeout duration and monitor the application for inactivity.  If there has not been any user interaction for the specified amount of time, a dialog will pop up and give the user an additional 30 seconds to respond otherwise the application will kill itself.

Make sure to add to your gradle:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
    
    
    	dependencies {
	        compile 'com.github.buradd:TimeoutSensor:1.6'
	}

To use, you must be using AppCompat - and replace each Activity extention with TimeoutCompatActivity:
    
    public class MainActivity extends TimeoutCompatActivity {
    
    }


Then, start the sensor and provide the duration (in minutes.) (This must only be called once, preferably from your MainActivity's onCreate method):

    //This will start the sensor to check for 15 minutes of inactivity.
    TimeoutSensor.start(15);
   

You can also set the duration and call start separately:

    TimeoutSensor.setTimeoutDuration(15);
    TimeoutSensor.start();

You may stop the sensor at any time:

    TimeoutSensor.stop();
    
    
There is a sample APK available here:
https://github.com/buradd/TimeoutSensor/blob/master/sample/app/TimeoutSensorSample.apk


That's it!
