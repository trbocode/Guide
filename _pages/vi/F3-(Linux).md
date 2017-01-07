---
title: "F3 (Linux)"
permalink: /f3-(linux).html
lang: vi
ref: f3-(linux)
---

This page will walk you through the process of checking your SD card for errors using F3.
{: .notice}

Depending on the size of your SD card and the speed of your computer, this process can take up to several hours!
{: .notice--info}

This page is for Linux users only. If you are not on Linux, check out the [H2testw (windows)](h2testw-(windows)) or [F3X (mac)](f3x-(mac)) pages.
{: .notice--info}

#### What you need

* The latest version of [F3](https://github.com/AltraMayor/f3/archive/v6.0.zip)

#### Instructions

1. Unzip the f3 `.zip` file
2. `cd` into the f3 directory
3. Run `make` to compile F3
4. Insert your SD card into your computer
5. Mount your SD card
6. Run `./f3write <your sd card mount point>`
7. Wait until the process is complete. See below for an example output.

		$ ./f3write /media/michel/6135-3363/
		Free space: 29.71 GB
		Creating file 1.h2w ... OK!
		...
		Creating file 30.h2w ... OK!
		Free space: 0.00 Byte
		Average Writing speed: 4.90 MB/s

8. Run `./f3read <your sd card mount point>`
9. Wait until the process is complete. See below for an example output.

		$ ./f3read /media/michel/6135-3363/
		                  SECTORS      ok/corrupted/changed/overwritten
		Validating file 1.h2w ... 2097152/        0/      0/      0
		...
		Validating file 30.h2w ... 1491904/        0/      0/      0

		  Data OK: 29.71 GB (62309312 sectors)
		Data LOST: 0.00 Byte (0 sectors)
			       Corrupted: 0.00 Byte (0 sectors)
			Slightly changed: 0.00 Byte (0 sectors)
			     Overwritten: 0.00 Byte (0 sectors)
		Average Reading speed: 9.42 MB/s


If the test shows the result `Data LOST: 0.00 Byte (0 sectors)` your SD card is good and you can delete all `.h2w` files on the SD card
{: .notice--success}

If the test shows any other results, your SD card may be corrupted or damaged and you may have to replace it!
{: .notice--danger}

Return to [Get Started](get-started)
{: .notice--primary}
