#!/usr/bin/env python
import time
import subprocess
import os

pcr0 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr1 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr2 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr3 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr4 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr5 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr6 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr7 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr8 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr9 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr10 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"
pcr14 = "Paste reference PCR Value here from /sys/class/tpm/tpm0/pcr-sha256/"

f0 = open("/sys/class/tpm/tpm0/pcr-sha256/0", "r")
f1 = open("/sys/class/tpm/tpm0/pcr-sha256/1", "r")
f2 = open("/sys/class/tpm/tpm0/pcr-sha256/2", "r")
f3 = open("/sys/class/tpm/tpm0/pcr-sha256/3", "r")
f4 = open("/sys/class/tpm/tpm0/pcr-sha256/4", "r")
f5 = open("/sys/class/tpm/tpm0/pcr-sha256/5", "r")
f6 = open("/sys/class/tpm/tpm0/pcr-sha256/6", "r")
f7 = open("/sys/class/tpm/tpm0/pcr-sha256/7", "r")
f8 = open("/sys/class/tpm/tpm0/pcr-sha256/8", "r")
f9 = open("/sys/class/tpm/tpm0/pcr-sha256/9", "r")
f10 = open("/sys/class/tpm/tpm0/pcr-sha256/10", "r")
f14 = open("/sys/class/tpm/tpm0/pcr-sha256/14", "r")

r0 = f0.read().replace("\n", "")
r1 = f1.read().replace("\n", "")
r2 = f2.read().replace("\n", "")
r3 = f3.read().replace("\n", "")
r4 = f4.read().replace("\n", "")
r5 = f5.read().replace("\n", "")
r6 = f6.read().replace("\n", "")
r7 = f7.read().replace("\n", "")
r8 = f8.read().replace("\n", "")
r9 = f9.read().replace("\n", "")
r10 = f10.read().replace("\n", "")
r14 = f14.read().replace("\n", "")

time.sleep(0.1)
if pcr0 != r0:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Failure' 'PCR0 (Core Root of Trust of Measurement (CRTM), BIOS, and Platform Extensions) has changed'""")
if pcr2 != r2:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Failure' 'PCR2 (Firmware/Option ROM Code) has changed'""")
if pcr3 != r3:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Failure' 'PCR3 (Firmware/Option ROM Configuration and Data) has changed'""")
if pcr6 != r6:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Failure' 'PCR6 (State Transition and Wake Events) has changed'""")
if pcr7 != r7:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Failure' 'PCR7 (Certificates, Secure Boot, and SBAT) has changed'""")
if pcr14 != r14:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Failure' 'PCR14 (MokList, MokListX, and MokSBState) has changed'""")


if pcr0 == r0 and pcr2 == r2 and pcr3 == r3 and pcr6 == r6 and pcr7 == r7 and pcr14 == r14:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Success' 'No changes detected'""")
	os.system("""sudo /usr/bin/systemctl start wg-quick@<Your Wireguard conf file here>""")

else:
	os.system("""sudo -u <Paste your userid here> DISPLAY=:0 DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus notify-send -u critical 'TPM Security Failure' 'Network Disabled'""")
