# packettracer-basic-security-lab

Hands-on Cisco CLI project covering secure configuration of switches and routers, including console/EXEC passwords, MOTD banners, and NVRAM saves.

**Lab type:** Packet Tracer (.pkt)  
**Topology:** PC1 → S1 → R1  
**Goal:** Practice secure baseline configuration on a Cisco switch and router.

---

## Objectives

1. Configure hostnames  
2. Configure passwords (Console + Privileged EXEC)  
3. Configure MOTD login banner  
4. Save configuration to NVRAM

---

## Step-by-Step Configuration

### Part 1 — Switch S1

**Step 1: Hostname**

`Switch> enable`

`Switch# configure terminal`

`Switch(config)# hostname S1`

`S1(config)#`

---

**Step 2: Console & Enable Passwords**

`S1(config)# line console 0`

`S1(config-line)# password cisco`

`S1(config-line)# login`

`S1(config-line)# exit`

`S1(config)# enable secret class`

---

**Step 3: Banner (MOTD)**

`S1(config)# banner motd #Authorized access only. Violators will be prosecuted.#`

---

**Step 4: Save to NVRAM**

`S1(config)# exit`

`S1# copy running-config startup-config`

---

### Part 2 — Router R1

**Step 1: Hostname & Enable Secret**

`Router> enable`

`Router# configure terminal`

`Router(config)# hostname R1`

`R1(config)# enable secret class`

---

**Step 2: Console Password**

`R1(config)# line console 0`

`R1(config-line)# password cisco`

`R1(config-line)# login`

`R1(config-line)# exit`

---

**Step 3: Banner (MOTD)**

`R1(config)# banner motd #Authorized access only. Violators will be prosecuted.#`

---

**Step 4: Save to NVRAM**

`R1(config)# exit`

`R1# copy running-config startup-config`

---

### Result

**Both S1 and R1 are configured with:**

1. Custom hostnames

2. Console & enable secret passwords
 
3. Security login banner

4. Saved configuration in NVRAM
