# Android emulator degrades bluetooth sound quality

After starting an Android emulator on a Mac the sound quality of a connected bluetooth headset can degrade. This happens because the emulator requests an access to a microphone which is the one built in to the connected bluetooth headset. MacOS provides the emulator with an access to the microphone and switches current bluetooth profile to a lower quality one used for speech. This degrades sound quality.

If microphone is not a required feature for your task, the microphone can be disabled in the emulator as follows:

* Open `Device Manager`, then click on the “three vertical dots” icon of the emulator.
* Choose `Show On Disk` option.
* In the opened `Finder` find and open for editing the `config.ini`file.
* Find `hw.audioInput` property and set it to `hw.audioInput = no`.
* Save changes and restart the emulator.