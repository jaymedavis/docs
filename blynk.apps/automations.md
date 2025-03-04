---
description: Automations let you set an automated control of your devices
---

# Automations

{% hint style="info" %}
Automations are replacement for old Blynk TimeInput, Timer, Bridge and Eventor widgets
{% endhint %}

{% hint style="warning" %}
Automations should be [enabled in Template settings](../blynk.console/templates/datastreams/datastreams-common-settings/automation.md) first. Otherwise, Automation tab will be unavailable in Blynk.Apps
{% endhint %}

![No automations](https://user-images.githubusercontent.com/72790181/120281222-57a77100-c2c1-11eb-82fc-5d872520671f.png)

Tap **Add automation** to create a new one

![Choose condition](https://user-images.githubusercontent.com/72790181/120281228-5b3af800-c2c1-11eb-8e54-267b8aed6e79.png)

If you don't see **Device state** condition that means you haven't enabled any datastream to work with automations. You need [to explicitly define](../blynk.console/templates/datastreams/datastreams-common-settings/automation.md) what datastreams will work as conditions.

Blynk currently supports 4 types of automations:

* **Time of Day** - allows you to trigger at a specific time of the day and for the specific day.
* **Sunset / Sunrise** - allows you to trigger at sunset/sunrise.

  This kind of automation is triggered based on the selected location.

  For the different locations you'll get the different sunset/sunrise time.

  Also, current sunset algorithm doesn't take into account the altitude of the selected region.

  So the sunset/sunrise time calculation may be not precise for the mountain regions.

* **Device state** - allows you to trigger based on the device datastream values. For example, if temperature &gt; 40 degrees turn of the boiler
* **Scene** - allows to manually trigger multiple actions. For example, set the temperature to 30 degrees and turn off the alarm.

  The visibility of scene automation is controlled via permission under the **Organizations** section and called **Automation execute**.

{% hint style="info" %}
Automations can work across multiple devices
{% endhint %}

* Create an Automation name
* Choose cover picture
* Set a condition that will trigger an automation

![No actions](https://user-images.githubusercontent.com/72790181/120281259-64c46000-c2c1-11eb-9b25-84c4e9e294b7.png)

After setting the condition you can **Add action** that will be performed when the condition is triggered

![Choose action type](https://user-images.githubusercontent.com/72790181/120281347-81f92e80-c2c1-11eb-989d-fb5832653d9f.png)

After pressing **Add action** button you’ll see a modal with types of actions. You can choose actions that will change the device’s state, send a notification to your smartphone or send an email to the specified address.

If you don't see **Set device to** action that means you haven't enabled any datastream to work with automations. You need [to explicitly define](../blynk.console/templates/datastreams/datastreams-common-settings/automation.md) what datastreams can work as actions.

![Automation ready](https://user-images.githubusercontent.com/72790181/120281482-ad7c1900-c2c1-11eb-95a7-7352d126ba73.png)

After adding the first action you can continue adding more of them or save this automation

![Automations tab](https://user-images.githubusercontent.com/72790181/120281496-b1a83680-c2c1-11eb-8f99-04188d31fce7.png)

When Automations are created you will see the list of them. Here you can disable/enable automations and open their settings for view and edit.

## Limit period

![Limit period \(tap on limit period\)](https://user-images.githubusercontent.com/72790181/120785065-6e55fe00-c535-11eb-8979-f3eb1b50ecf1.png)

All automations with **Device state** condition have a **limit period**. Limit period defines a period during which only one condition trigger will be processed.

For example, let's say we set a condition **when temperature is greater than 20 degrees** and **limit period is set to one hour**.

At 9:30 device sends the temperature 21 degrees. Automation will be triggered and automation actions are executed.

At 9:40 device sends the temperature 22 degrees. Automation will not be triggered in that case, because we have a limit period set to one hour.

At 10:31 device sends the temperature 22 degrees. Automation will be triggered and automation actions are executed again, as ignore period \(one hour\) had already passed since the last execution.

