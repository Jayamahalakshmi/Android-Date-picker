# Android-Date-picker

Project Abstract:

Datepicker is an app in which the user can easily change the date with (day/month/year).  User can pick any date they want. It is available in English. The project has been developed in java.
     
ProductScope:

This is a Software Requirements Specification (SRS) document for Datepicker(version1.0). Its purpose is to describe functional requirements, features and other important requirements for this system’s function. 

Userdocumentation:

Datepicker is a program which will soon get released. Therefore, the SRS document intends to make clear already implemented features of the software, and to write down requirements for future extensions. This document may be used as a guide for those who want to understand the existing features of the program and for those who want to develop future components of the program.

Assumptions and Dependencies:

•There is 1 user using the app on a single system.

•The system should be in working condition.

•When we open the app it asks to set date and also it shows some random date. With the use of this app we can easily Set the current date.

Functional Requirements:

1.Displaying a button: This button is required to set a date

2.Displaying ok button: This button used to save all the changes made by the user Specific Requirements:

• Software interface : It requires at least of android11.
• HardwareInterfaces : This application is built by java and it need at least some minimum hardware requirements of 1GB of RAM and 1GHz processor.
• UserInterfaces : The user interface for the Datepicker app is the ok button.It saves changes made by the user.

Program:

activity_main.xml:

<?xmlversion="1.0"encoding="utf-8"?>

<RelativeLayout

xmlns:android="http://schemas.android.com/apk/res/android"

xmlns:tools="http://schemas.android.com/tools"

android:layout_width="match_parent"

android:layout_height="match_parent"

android:paddingBottom="@dimen/activity_vertical_margin"

android:paddingLeft="@dimen/activity_horizontal_margin"

android:paddingRight="@dimen/activity_horizontal_margin"

android:paddingTop="@dimen/activity_vertical_margin"

tools:context=".MainActivity">

<Button

android:id="@+id/button1"

android:layout_width="wrap_content"

android:layout_height="wrap_content"

android:layout_alignParentTop="true"

android:layout_centerHorizontal="true"

android:layout_marginTop="70dp"

android:onClick="setDate"

android:text="@string/date_button_set"/>

<TextView

android:id="@+id/textView1"

android:layout_width="wrap_content"

android:layout_height="wrap_content"

android:layout_alignParentTop="true"

android:layout_centerHorizontal="true"

android:layout_marginTop="24dp"

android:text="@string/date_label_set"

android:textAppearance="?android:attr/textAppearanceMedium"/>

<TextView

android:id="@+id/textView2"

android:layout_width="wrap_content"

android:layout_height="wrap_content"

android:layout_below="@+id/button1"

android:layout_marginTop="66dp"

android:layout_toLeftOf="@+id/button1"

android:text="@string/date_view_set"

android:textAppearance="?android:attr/textAppearanceMedium"/>

<TextView

android:id="@+id/textView3"

android:layout_width="wrap_content"

android:layout_height="wrap_content"

android:layout_alignRight="@+id/button1"

android:layout_below="@+id/textView2"

android:layout_marginTop="72dp"

android:text="@string/date_selected"

android:textAppearance="?android:attr/textAppearanceMedium"/>

</RelativeLayout>

Dimens.xml

<?xmlversion="1.0"encoding="utf-8"?>

<resources>

<dimen name="activity_vertical_margin">8dp</dimen>

<dimen name="activity_horizontal_margin">8dp</dimen>

</resources>

Strings.xml

?xmlversion="1.0"encoding="utf-8"?>

<resources>

<string name="app_name">DatePicker</string>

<string name="action_settings">Settings</string>

<string name="hello_world">Helloworld!</string>

<string name="date_label_set">Pressthebuttontosetthedate</string>

<string name="date_button_set">SetDate</string>

<string name="date_view_set">TheDateis:</string>

<string name="date_selected"></string>

</resources>

MainActivity.java:

package com.example.datepicker;

import java.util.Calendar;

import android.app.Activity;

import android.app.DatePickerDialog;

import android.app.Dialog;

import android.os.Bundle;

import android.view.Menu;

import android.view.View;

import android.widget.DatePicker;

import android.widget.TextView;

import android.widget.Toast;

public class Main Activity extends Activity{

private DatePicker datePicker;

private Calendar calendar;

private TextView dateView;

private int year, month, day;

@Override

protected void on Create(Bundle savedInstanceState){

super.onCreate(savedInstanceState);

setContentView(R.layout.activity_main);

dateView=(TextView)findViewById(R.id.textView3);

calendar=Calendar.getInstance();

year=calendar.get(Calendar.YEAR);

month=calendar.get(Calendar.MONTH);

day=calendar.get(Calendar.DAY_OF_MONTH);

showDate(year,month+1,day);

}

@SuppressWarnings("deprecation")

public void setDate(View view){

showDialog(999);

Toast.makeText(getApplicationContext(),"ca",

Toast.LENGTH_SHORT)

.show();

}

@Override

protected Dialog on Create Dialog(intid){

//TODO Auto-generated method stub

if(id==999){

return new Date PickerDialog(this,myDateListener,year,month,day);

}

return null;

}

private DatePickerDialog.OnDateSetListener myDateListener=new

DatePickerDialog.OnDateSetListener(){

@Override

public void onDateSet(DatePickerarg0,

intarg1,intarg2,intarg3){

//TODO Auto-generated method stub

//arg1=year

//arg2=month

//arg3=day

showDate(arg1,arg2+1,arg3);

}

};

private void showDate(intyear,intmonth,intday){

dateView.setText(newStringBuilder().append(day).append("/")

.append(month).append("/").append(year));

}

}

OUTPUT:


![IMG_20220706_230110](https://user-images.githubusercontent.com/104053532/177609554-0ba3ba4a-ac62-4905-9c59-212fe7bcc134.jpg)

RESULT:

Thus, the implementation of the Date picker App has been implemented and the output has been verified successfully.
