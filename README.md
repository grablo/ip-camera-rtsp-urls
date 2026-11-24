# IP camera RTSP URLs by brand

RTSP URL paths for 61 IP camera and NVR manufacturers (94 paths), each with a link to the official manufacturer document or the cited open dataset it comes from.

Want a URL built for you? Use the free [RTSP URL generator](https://litmusnvr.com/rtsp-url-generator). To record and search these cameras for free, see [Litmus NVR](https://litmusnvr.com).

The same data is available as JSON in [data/rtsp-urls.json](data/rtsp-urls.json).

## What is an RTSP URL?

RTSP (Real Time Streaming Protocol) is how most IP cameras and NVRs serve live video on the local network. An RTSP URL has this form:

```
rtsp://user:password@IP:554/path
```

- `user:password`: the camera or NVR login. Special characters in the password must be URL-encoded (for example `@` becomes `%40`).
- `IP`: the camera's address on your network.
- `554`: the RTSP port. 554 is the standard default; some brands use another port (shown under each brand).
- `/path`: the brand-specific part listed below.

Most cameras offer a main stream (full resolution) and a sub stream (lower resolution, lighter on bandwidth). The examples below use `admin:password` and `192.168.1.100`; replace them with your own values.

### Test a URL in VLC

1. Open VLC and choose **Media > Open Network Stream**.
2. Paste the RTSP URL and click **Play**.

If it fails, check that RTSP is enabled on the camera, the user name and password are correct, and the port matches.

## Placeholders

Templates use these placeholders for the channel number (the camera number on an NVR or the input on an encoder). The examples fill in channel 1.

| Placeholder | Meaning | Channel 1 | Channel 12 |
|---|---|---|---|
| `{ch}` | Channel number | `1` | `12` |
| `{ch2}` | Channel number, two digits | `01` | `12` |
| `{ch0}` | Channel number minus 1 (zero-based) | `0` | `11` |
| `{ch02}` | Channel number minus 1, two digits | `00` | `11` |
| `{ch3}` | Channel number, three digits | `001` | `012` |

## Contents

- **A**: [ACTi](#acti-rtsp-url) · [ADT](#adt-rtsp-url) · [Alptop](#alptop-rtsp-url) · [Amcrest](#amcrest-rtsp-url) · [Annke](#annke-rtsp-url) · [Arecont Vision (Costar)](#arecont-vision-costar-rtsp-url) · [Avigilon](#avigilon-rtsp-url) · [Axis](#axis-rtsp-url)
- **B**: [Bosch](#bosch-rtsp-url)
- **D**: [D-Link](#d-link-rtsp-url) · [Dahua](#dahua-rtsp-url) · [dbell](#dbell-rtsp-url) · [Digital Watchdog](#digital-watchdog-rtsp-url) · [DoorBird](#doorbird-rtsp-url)
- **E**: [EZVIZ](#ezviz-rtsp-url)
- **F**: [Foscam](#foscam-rtsp-url)
- **G**: [GeoVision](#geovision-rtsp-url) · [Grandstream](#grandstream-rtsp-url)
- **H**: [Hanwha Vision (Wisenet)](#hanwha-vision-wisenet-rtsp-url) · [Hanwha Vision NVR (Wisenet)](#hanwha-vision-nvr-wisenet-rtsp-url) · [Hikvision](#hikvision-rtsp-url) · [Honeywell](#honeywell-rtsp-url)
- **I**: [IC Realtime](#ic-realtime-rtsp-url) · [IDIS](#idis-rtsp-url) · [IeGeek](#iegeek-rtsp-url) · [InVid Tech](#invid-tech-rtsp-url) · [IONODES](#ionodes-rtsp-url) · [IPCcam](#ipccam-rtsp-url) · [ipTIME](#iptime-rtsp-url)
- **L**: [LILIN](#lilin-rtsp-url) · [Lorex](#lorex-rtsp-url)
- **M**: [Matrix](#matrix-rtsp-url) · [Microseven](#microseven-rtsp-url) · [Milesight](#milesight-rtsp-url) · [Mobotix](#mobotix-rtsp-url)
- **O**: [OVISS](#oviss-rtsp-url)
- **P**: [Panasonic / i-PRO](#panasonic--i-pro-rtsp-url) · [Pelco](#pelco-rtsp-url) · [Provision-ISR](#provision-isr-rtsp-url)
- **Q**: [Q-See](#q-see-rtsp-url)
- **R**: [Reolink](#reolink-rtsp-url) · [Revo](#revo-rtsp-url)
- **S**: [Samsung Techwin (legacy)](#samsung-techwin-legacy-rtsp-url) · [Sharx Security](#sharx-security-rtsp-url) · [Sony](#sony-rtsp-url) · [Sricam](#sricam-rtsp-url) · [Swann](#swann-rtsp-url)
- **T**: [Techview](#techview-rtsp-url) · [TP-Link Tapo](#tp-link-tapo-rtsp-url) · [TP-Link VIGI](#tp-link-vigi-rtsp-url) · [TRENDnet](#trendnet-rtsp-url) · [TRUEN](#truen-rtsp-url) · [TVT](#tvt-rtsp-url) · [Tyco Illustra](#tyco-illustra-rtsp-url)
- **U**: [Ubiquiti UniFi](#ubiquiti-unifi-rtsp-url) · [Uniview](#uniview-rtsp-url)
- **V**: [Vivotek](#vivotek-rtsp-url)
- **W**: [Wansview](#wansview-rtsp-url)
- **Z**: [Zavio](#zavio-rtsp-url) · [Zmodo](#zmodo-rtsp-url) · [Zosi](#zosi-rtsp-url)
- [Unknown brand — common paths](#unknown-brand--common-paths)

## ACTi RTSP URL

Default port: 554

### ACTi: path 1

VLC guide for current models ('stream#'). The port differs by camera.

- Main stream: `rtsp://admin:password@192.168.1.100:554/stream1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/stream2`
- Template: main `/stream1`, sub `/stream2`
- Source: http://download.acti.com/?id=29560

### ACTi: path 2

Older models. CamioCam values: 1 high quality, 3 low quality.

- Main stream: `rtsp://admin:password@192.168.1.100:7070/track1`
- Sub stream: `rtsp://admin:password@192.168.1.100:7070/track3`
- Third stream: `rtsp://admin:password@192.168.1.100:7070/track2`
- Template: main `/track1`, sub `/track3`, third `/track2`
- Port for this path: 7070
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'ACTi A82 Dome'; maker doc cited by CamioCam: http://www2.acti.com/getfile/KnowledgeBase_UploadFile/Third_Party_or_Open_Source_Software_Integration_20100402_006.pdf

## ADT RTSP URL

Default port: 554

NVR channels 1-4.

- Main stream: `rtsp://admin:password@192.168.1.100:554/trackID=1`
- Template: main `/trackID={ch}`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'ADT A-ADT4H2S'

## Alptop RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/0`
- Template: main `/0`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Alptop AT_LIR400'

## Amcrest RTSP URL

Default port: 554

Same format as Dahua. Verified in the official Amcrest HTTP API PDF (the same document cited for Dahua).

- Main stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=1`
- Third stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=2`
- Template: main `/cam/realmonitor?channel={ch}&subtype=0`, sub `/cam/realmonitor?channel={ch}&subtype=1`, third `/cam/realmonitor?channel={ch}&subtype=2`
- Source: https://support.amcrest.com/hc/en-us/article_attachments/360012029291

## Annke RTSP URL

Default port: 554

Guide: [Annke RTSP URL and PC viewing](https://litmusnvr.com/annke-rtsp-url)

Frigate groups Annke with Hikvision and Uniview and uses this path. No official Annke documentation was found. The sub stream (102) would follow Hikvision's official formula, but it is not listed because there is no Annke source.

- Main stream: `rtsp://admin:password@192.168.1.100:554/Streaming/Channels/101`
- Template: main `/Streaming/Channels/101`
- Source: https://github.com/blakeblackshear/frigate/blob/dev/web/src/types/cameraWizard.ts (MIT) label 'Hikvision / Uniview / Annke'

## Arecont Vision (Costar) RTSP URL

Default port: 554

Official syntax 'res=half/full'; ssn is a unique value per stream. fps=0 is the CamioCam value.

- Main stream: `rtsp://admin:password@192.168.1.100:554/h264.sdp?res=full&doublescan=0&fps=0&ssn=1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/h264.sdp?res=half&doublescan=0&fps=0&ssn=2`
- Template: main `/h264.sdp?res=full&doublescan=0&fps=0&ssn=1`, sub `/h264.sdp?res=half&doublescan=0&fps=0&ssn=2`
- Source: https://sales.arecontvision.com/marketing/contents/Integration_QSG_001_ENG_001.pdf

## Avigilon RTSP URL

Default port: 554

### Avigilon: path 1

H.264 cameras. The official documentation gives no sub stream path.

- Main stream: `rtsp://admin:password@192.168.1.100:554/defaultPrimary?streamType=u`
- Template: main `/defaultPrimary?streamType=u`
- Source: https://www.avigilon.com/fs/documents/avigilon-fisheye-web-interface-user-guide-en.pdf

### Avigilon: path 2

ENC encoders, channels 0-3.

- Main stream: `rtsp://admin:password@192.168.1.100:554/defaultPrimary0?streamtype=u`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/defaultSecondary0?streamtype=u`
- Template: main `/defaultPrimary{ch0}?streamtype=u`, sub `/defaultSecondary{ch0}?streamtype=u`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Avigilon ENC-4P-H264'; maker doc cited by CamioCam: http://avigilon.com/assets/Uploads/UG-H3A-Rev1UserGuide.pdf

## Axis RTSP URL

Default port: 554

Guide: [Axis RTSP URL and PC viewing](https://litmusnvr.com/axis-rtsp-url)

### Axis: path 1

The sub stream is the same stream scaled down with the resolution parameter. 640x480 is an example value chosen for this list and must be a resolution the camera supports (the official example uses 1920x1080).

- Main stream: `rtsp://admin:password@192.168.1.100:554/axis-media/media.amp`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/axis-media/media.amp?resolution=640x480`
- Template: main `/axis-media/media.amp`, sub `/axis-media/media.amp?resolution=640x480`
- Source: https://developer.axis.com/video-streaming-and-recording/video-streaming/how-to-guides/rtsp/

### Axis: path 2

Multi-channel encoders and multi-sensor cameras. camera defaults to 1.

- Main stream: `rtsp://admin:password@192.168.1.100:554/axis-media/media.amp?camera=1`
- Template: main `/axis-media/media.amp?camera={ch}`
- Source: https://developer.axis.com/video-streaming-and-recording/video-streaming/how-to-guides/configure-channel-defaults/

### Axis: path 3

Older MPEG-4 models.

- Main stream: `rtsp://admin:password@192.168.1.100:554/mpeg4/media.amp`
- Template: main `/mpeg4/media.amp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Axis 207W'; maker doc cited by CamioCam: http://www.axis.com/files/manuals/um_207w_mw_33158_en_1208.pdf

### Axis: path 4

241Q video server, channels 1-4.

- Main stream: `rtsp://admin:password@192.168.1.100:554/mpeg4/1/media.amp`
- Template: main `/mpeg4/{ch}/media.amp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Axis 241Q'; maker doc cited by CamioCam: https://www.axis.com/files/manuals/um_241S_241Q_36455__en_0908.pdf

## Bosch RTSP URL

Default port: 554

### Bosch: path 1

VIP cameras and encoders (now in the Keenfinity knowledge base).

- Main stream: `rtsp://admin:password@192.168.1.100:554/?inst=1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/?inst=2`
- Template: main `/?inst=1`, sub `/?inst=2`
- Source: https://knowledge.keenfinity-group.com/video-systems/article/how-is-rtsp-usage-supported-with-bosch-vip-devices

### Bosch: path 2

Multi-input encoders.

- Main stream: `rtsp://admin:password@192.168.1.100:554/?line=1&inst=1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/?line=1&inst=2`
- Template: main `/?line={ch}&inst=1`, sub `/?line={ch}&inst=2`
- Source: https://knowledge.keenfinity-group.com/video-systems/article/how-is-rtsp-usage-supported-with-bosch-vip-devices

### Bosch: path 3

Tunneled over HTTP (port 80); may not work on 554.

- Main stream: `rtsp://admin:password@192.168.1.100:80/rtsp_tunnel`
- Template: main `/rtsp_tunnel`
- Port for this path: 80
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Bosch'; maker doc cited by CamioCam: http://resource.boschsecurity.us/documents/Installation_Manual_enUS_1997482635.pdf

## D-Link RTSP URL

Default port: 554

### D-Link: path 1

CamioCam: 1 high quality, 3 low quality.

- Main stream: `rtsp://admin:password@192.168.1.100:554/live1.sdp`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/live3.sdp`
- Third stream: `rtsp://admin:password@192.168.1.100:554/live2.sdp`
- Template: main `/live1.sdp`, sub `/live3.sdp`, third `/live2.sdp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'D-Link DCS-2332'; maker doc cited by CamioCam: http://www.dlink.com/-/media/Consumer_Products/DCS/DCS%202332L/Manual/DCS_2332L_A1_Manual_v100_WW.pdf

### D-Link: path 2

- Main stream: `rtsp://admin:password@192.168.1.100:554/play1.sdp`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/play3.sdp`
- Third stream: `rtsp://admin:password@192.168.1.100:554/play2.sdp`
- Template: main `/play1.sdp`, sub `/play3.sdp`, third `/play2.sdp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'D-Link DCS-960L;DCS-936L;DCS-2630L'; maker doc cited by CamioCam: ftp://ftp2.dlink.com/PRODUCTS/DCS-960L/REVA/DCS-960L_REVA_MANUAL_1.00_EN_US.PDF

## Dahua RTSP URL

Default port: 554

Guide: [Dahua RTSP URL and PC viewing](https://litmusnvr.com/dahua-rtsp-url)

channel starts at 1; on an NVR, use the channel number. subtype: 0 main, 1 sub stream 1, 2 sub stream 2. A stream that is disabled or does not exist returns an error.

- Main stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=1`
- Third stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=2`
- Template: main `/cam/realmonitor?channel={ch}&subtype=0`, sub `/cam/realmonitor?channel={ch}&subtype=1`, third `/cam/realmonitor?channel={ch}&subtype=2`
- Source: https://material.dahuasecurity.com/uploads/cpq/DOR/PUM0001826/Dahua-Network-Camera-Web-5.0_Operation-Manual_V1.0.6.pdf; https://support.amcrest.com/hc/en-us/article_attachments/360012029291 (Amcrest HTTP API, 4.1.1 Get real-time stream, pp. 17-18); same wording in the Dahua CGI document https://ftp.asm.cz/Dahua/kamerove_systemy/SDK&API/CGI_snapshot,stream.pdf (distributor's copy)

## dbell RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/av0_0`
- Template: main `/av0_0`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Dbell HD+'

## Digital Watchdog RTSP URL

Default port: 554

### Digital Watchdog: path 1

MEGApix Core Pro / Value.

- Main stream: `rtsp://admin:password@192.168.1.100:554/profile1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/profile2`
- Template: main `/profile1`, sub `/profile2`
- Source: https://support.digital-watchdog.com/hc/en-us/articles/43284896070548

### Digital Watchdog: path 2

COVA recorders.

- Main stream: `rtsp://admin:password@192.168.1.100:554/chID=1&streamType=main&linkType=tcp`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/chID=1&streamType=sub&linkType=tcp`
- Template: main `/chID={ch}&streamType=main&linkType=tcp`, sub `/chID={ch}&streamType=sub&linkType=tcp`
- Source: https://support.digital-watchdog.com/hc/en-us/articles/43283607580564

### Digital Watchdog: path 3

VMAX IP G4 / A1 G4.

- Main stream: `rtsp://admin:password@192.168.1.100:554/main/ch1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/sub/ch1`
- Template: main `/main/ch{ch}`, sub `/sub/ch{ch}`
- Source: https://support.digital-watchdog.com/hc/en-us/articles/43283607580564

### Digital Watchdog: path 4

Older VMAX.

- Main stream: `rtsp://admin:password@192.168.1.100:554/rtsp/unicast/live/profile-1`
- Template: main `/rtsp/unicast/live/profile-{ch}`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Digital Watchdog VMAX A1 / IP Plus'

## DoorBird RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/mpeg/media.amp`
- Template: main `/mpeg/media.amp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'DoorBird Doorbell Camera'; maker doc cited by CamioCam: http://www.doorbird.com/downloads/api_lan.pdf?rev=0.13

## EZVIZ RTSP URL

Default port: 554

Guide: [EZVIZ RTSP URL and PC viewing](https://litmusnvr.com/ezviz-rtsp-url)

Official guide for C6N/TY1/TY2. The password is the verification code on the device label. The official documentation gives no sub stream path.

- Main stream: `rtsp://admin:password@192.168.1.100:554/ch1/main`
- Template: main `/ch1/main`
- Source: https://m-support.ezviz.com/product/TY1/27458

## Foscam RTSP URL

Default port: 88

Guide: [Foscam RTSP URL and PC viewing](https://litmusnvr.com/foscam-rtsp-url)

On most models this is the same as the HTTP port (default 88). Some later revisions of the C1 and FI98xx use 554.

- Main stream: `rtsp://admin:password@192.168.1.100:88/videoMain`
- Sub stream: `rtsp://admin:password@192.168.1.100:88/videoSub`
- Template: main `/videoMain`, sub `/videoSub`
- Source: https://www.foscam.com/faqs/view.html?id=81

## GeoVision RTSP URL

Default port: 8554

{ch3} = zero-padded to three digits (CH001). Sub stream path not verified.

- Main stream: `rtsp://admin:password@192.168.1.100:8554/CH001.sdp`
- Template: main `/CH{ch3}.sdp`
- Source: http://pd.geovision.tw/faq/IPDevice/RTSP_protocol-j_revised6.pdf

## Grandstream RTSP URL

Default port: 554

### Grandstream: path 1

GSC361x.

- Main stream: `rtsp://admin:password@192.168.1.100:554/0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/4`
- Template: main `/0`, sub `/4`
- Source: https://www.grandstream.com/hubfs/Product_Documentation/GSC36XX_usermanual.pdf

### Grandstream: path 2

GXV3504 encoder, channels 0-7.

- Main stream: `rtsp://admin:password@192.168.1.100:554/0`
- Template: main `/{ch0}`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Grandstream GXV3504'; maker doc cited by CamioCam: http://www.voipsupply.com/downloads/dl/file/id/8911/grandstream_gxv3504_manual.pdf

## Hanwha Vision (Wisenet) RTSP URL

Default port: 554

Guide: [Hanwha Vision RTSP URL and PC viewing](https://litmusnvr.com/hanwha-rtsp-url)

### Hanwha Vision (Wisenet): path 1

The profile number is the number in the camera's video profile list. The official documentation does not say which numbers are main and sub (it varies by device), so no sub stream is listed. Hanwha official documentation: the default H.264 stream is profile 2, the default H.265 stream is profile 3, and fisheye cameras have only one default profile.

- Main stream: `rtsp://admin:password@192.168.1.100:554/profile2/media.smp`
- Template: main `/profile2/media.smp`
- Source: https://support.hanwhavision.com/hc/ko/articles/47257361792659; https://support.hanwhavision.com/hc/en-001/articles/47256874514195-How-to-use-Hanwha-cameras-with-exacqVision

### Hanwha Vision (Wisenet): path 2

Multi-sensor cameras and encoders. Sensor numbers start at 0 ({ch0} = channel - 1). Matches the CamioCam 'Hanwha multi-sensor' row.

- Main stream: `rtsp://admin:password@192.168.1.100:554/0/profile2/media.smp`
- Template: main `/{ch0}/profile2/media.smp`
- Source: https://support.hanwhavision.com/hc/en-001/articles/47782445700243

## Hanwha Vision NVR (Wisenet) RTSP URL

Default port: 558

Guide: [Hanwha Vision RTSP URL and PC viewing](https://litmusnvr.com/hanwha-rtsp-url)

Channels start at 0. The port is the last value of the NVR's device port range (558 if the range is 554-558). A stream is selected with the form '/media.smp/profile=<n>'.

- Main stream: `rtsp://admin:password@192.168.1.100:558/LiveChannel/0/media.smp`
- Template: main `/LiveChannel/{ch0}/media.smp`
- Source: https://support.hanwhavision.com/hc/en-001/articles/47257331451667

## Hikvision RTSP URL

Default port: 554

Guide: [Hikvision RTSP URL and PC viewing](https://litmusnvr.com/hikvision-rtsp-url)

### Hikvision: path 1

IP cameras: ch=1. NVRs: channel x 100 + stream (01 main, 02 sub). On hybrid DVRs, IP channels continue after the analog channels (e.g. 1701 = first IP camera; source: https://us-legacy.hikvision.com/sites/default/files/tb/tb_rtsp_and_http_urls_120915us.pdf).

- Main stream: `rtsp://admin:password@192.168.1.100:554/Streaming/Channels/101`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/Streaming/Channels/102`
- Template: main `/Streaming/Channels/{ch}01`, sub `/Streaming/Channels/{ch}02`
- Source: https://supportusa.hikvision.com/support/solutions/articles/17000129064-how-do-i-get-my-rtsp-stream-

### Hikvision: path 2

ID = channel x 100 + stream (1 main, 2 sub, 3 third). 103 is derived from the official formula; the documentation gives no example of it.

- Main stream: `rtsp://admin:password@192.168.1.100:554/ISAPI/Streaming/channels/101`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/ISAPI/Streaming/channels/102`
- Third stream: `rtsp://admin:password@192.168.1.100:554/ISAPI/Streaming/channels/103`
- Template: main `/ISAPI/Streaming/channels/{ch}01`, sub `/ISAPI/Streaming/channels/{ch}02`, third `/ISAPI/Streaming/channels/{ch}03`
- Source: https://enpinfo.hikvision.com/unzip/20201110210551_77443_doc/GUID-515FF2B5-5E01-4F03-8B81-4CA5BD621965.html

### Hikvision: path 3

Fixed candidate path used by Frigate (no channel number).

- Main stream: `rtsp://admin:password@192.168.1.100:554/Streaming/Channels/1`
- Template: main `/Streaming/Channels/1`
- Source: https://github.com/blakeblackshear/frigate/blob/dev/frigate/api/camera.py

### Hikvision: path 4

Old PSIA path (2013-era DS-2CD20xx, etc.).

- Main stream: `rtsp://admin:password@192.168.1.100:554/PSIA/streaming/channels/101`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/PSIA/streaming/channels/102`
- Template: main `/PSIA/streaming/channels/101`, sub `/PSIA/streaming/channels/102`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Hikvision DS-2CD2032-I etc.'; maker doc cited by CamioCam: http://www.hikvision.com/UploadFile/image/2013061411054615328.pdf

## Honeywell RTSP URL

Default port: 554

35 Series. Format rtsp://IP:port/live/<camera ID>/<stream ID>; stream ID 1 main, 2 sub, 3 third. The official example uses camera ID 1. The video mode must be set to H.264/H.265. Other series (30, 60, 70, older equIP) may use different paths.

- Main stream: `rtsp://admin:password@192.168.1.100:554/live/1/1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/live/1/2`
- Third stream: `rtsp://admin:password@192.168.1.100:554/live/1/3`
- Template: main `/live/{ch}/1`, sub `/live/{ch}/2`, third `/live/{ch}/3`
- Source: https://hbtmkto.honeywell.com/rs/127-UCB-316/images/800-26904-A_Honeywell%2035%20Series%20Cameras%20User%20Guide_JP.pdf (Honeywell 35 Series Cameras User Guide 800-26904-A, pp. 53-54)

## IC Realtime RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=1`
- Template: main `/cam/realmonitor?channel={ch}&subtype=0`, sub `/cam/realmonitor?channel={ch}&subtype=1`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'IC Realtime NVR / Camera'; maker doc cited by CamioCam: http://icrealtime.com/docs/product-manual/Man_NVR716N.pdf

## IDIS RTSP URL

Default port: 554

### IDIS: path 1

Cameras. Official wording: camera rtsp://ID:password@IP:RTSP port/trackID='Stream number'; NVR/TVR rtsp://.../trackID=<camera-number>&streamID=<stream-number>; default port 554. The FAQ does not say which number is the main stream (1 = main, 2 = sub has no official basis). The YouTube example in the same FAQ uses trackID=1.

- Main stream: `rtsp://admin:password@192.168.1.100:554/trackID=1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/trackID=2`
- Template: main `/trackID=1`, sub `/trackID=2`
- Source: https://www.idisglobal.com/index/faq/page/165?numIndex=2 (IDIS official FAQ #872 "What are the RTSP Address URL for each products?", 2020-05-12)

### IDIS: path 2

NVRs: trackID = camera number, streamID = stream quality. Official wording: camera rtsp://ID:password@IP:RTSP port/trackID='Stream number'; NVR/TVR rtsp://.../trackID=<camera-number>&streamID=<stream-number>; default port 554. The FAQ does not say which number is the main stream (1 = main, 2 = sub has no official basis). The YouTube example in the same FAQ uses trackID=1.

- Main stream: `rtsp://admin:password@192.168.1.100:554/trackID=1&streamID=1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/trackID=1&streamID=2`
- Template: main `/trackID={ch}&streamID=1`, sub `/trackID={ch}&streamID=2`
- Source: https://www.idisglobal.com/index/faq/page/165?numIndex=2 (IDIS official FAQ #872 "What are the RTSP Address URL for each products?", 2020-05-12)

## IeGeek RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/11`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/12`
- Template: main `/11`, sub `/12`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'IeGeek CT0247US'

## InVid Tech RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/mode=real&idc=1&ids=1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/mode=real&idc=1&ids=3`
- Third stream: `rtsp://admin:password@192.168.1.100:554/mode=real&idc=1&ids=2`
- Template: main `/mode=real&idc=1&ids=1`, sub `/mode=real&idc=1&ids=3`, third `/mode=real&idc=1&ids=2`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'InVid ELEV-P4SMOKE'

## IONODES RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/videoinput_1/h264_1/media.stm`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/videoinput_1/h264_2/media.stm`
- Template: main `/videoinput_1/h264_1/media.stm`, sub `/videoinput_1/h264_2/media.stm`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'IONODE ION-E100'

## IPCcam RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/11`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/12`
- Third stream: `rtsp://admin:password@192.168.1.100:554/13`
- Template: main `/11`, sub `/12`, third `/13`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'IPCcam 9605E'

## ipTIME RTSP URL

Default port: 554

C400G, C500G, C400GS, C500GS. Turn on RTSP in the app; user name admin.

- Main stream: `rtsp://admin:password@192.168.1.100:554/onvif1`
- Template: main `/onvif1`
- Source: https://iptime.com/support/faq/26587

## LILIN RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/rtsph2641080p`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/rtsph264480p`
- Template: main `/rtsph2641080p`, sub `/rtsph264480p`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Lilin Camera'; maker doc cited by CamioCam: https://lilin.zendesk.com/hc/en-gb/article_attachments/115002592986/LILIN_RTSP_JPEG_and_H.264_Streams_Guide.pdf

## Lorex RTSP URL

Default port: 554

### Lorex: path 1

Lorex official help: some recorder models (models not specified); 0 main, 1 sub. Matches the CamioCam NR9320N row.

- Main stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=1`
- Template: main `/cam/realmonitor?channel={ch}&subtype=0`, sub `/cam/realmonitor?channel={ch}&subtype=1`
- Source: https://www.lorex.com/blogs/help/ip-cameras-using-real-time-streaming-protocol-rtsp-with-your-dvr-nvr

### Lorex: path 2

LNE3003 standalone IP camera.

- Main stream: `rtsp://admin:password@192.168.1.100:554/video.mp4`
- Template: main `/video.mp4`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Lorex LNE3003'; maker doc cited by CamioCam: https://www.lorextechnology.com/downloads/ip-cameras/LN-Series/LNE3003i_Specs_R1.pdf

## Matrix RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/unicaststream/1`
- Template: main `/unicaststream/1`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Matrix 3MP Fixed'

## Microseven RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/11`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/13`
- Third stream: `rtsp://admin:password@192.168.1.100:554/12`
- Template: main `/11`, sub `/13`, third `/12`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Microseven M7XXX'

## Milesight RTSP URL

Default port: 554

### Milesight: path 1

IP cameras.

- Main stream: `rtsp://admin:password@192.168.1.100:554/main`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/sub`
- Third stream: `rtsp://admin:password@192.168.1.100:554/third`
- Template: main `/main`, sub `/sub`, third `/third`
- Source: https://www.milesight.com/support/download/document-center/ipc-series/ai/en/user-manual/rtsp.html

### Milesight: path 2

NVRs. The last two digits are the channel, starting at 00 ({ch02} = channel - 1, two digits). 1 main, 4 sub.

- Main stream: `rtsp://admin:password@192.168.1.100:554/ch_100`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/ch_400`
- Template: main `/ch_1{ch02}`, sub `/ch_4{ch02}`
- Source: https://www.milesight.com/support/download/document-center/nvr-series/qt/user-manual/more.html

## Mobotix RTSP URL

Default port: 554

Firmware with H.264 support.

- Main stream: `rtsp://admin:password@192.168.1.100:554/mobotix.h264`
- Template: main `/mobotix.h264`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Mobotix s16'; maker doc cited by CamioCam: https://www.mobotix.com/sites/default/files/2017-10/Mx_QI_S16_en_20171010.pdf

## OVISS RTSP URL

Default port: 8554

### OVISS: path 1

- Main stream: `rtsp://admin:password@192.168.1.100:8554/video1`
- Sub stream: `rtsp://admin:password@192.168.1.100:8554/video2`
- Third stream: `rtsp://admin:password@192.168.1.100:8554/video3`
- Template: main `/video1`, sub `/video2`, third `/video3`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'OVISS Camera'

### OVISS: path 2

NVRs.

- Main stream: `rtsp://admin:password@192.168.1.100:8554/unicast/c1-n/s0/live`
- Sub stream: `rtsp://admin:password@192.168.1.100:8554/unicast/c1-n/s1/live`
- Template: main `/unicast/c{ch}-n/s0/live`, sub `/unicast/c{ch}-n/s1/live`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'OVISS ProS'

## Panasonic / i-PRO RTSP URL

Default port: 554

### Panasonic / i-PRO: path 1

H.265-generation models (stream_4 also exists).

- Main stream: `rtsp://admin:password@192.168.1.100:554/Src/MediaInput/stream_1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/Src/MediaInput/stream_2`
- Third stream: `rtsp://admin:password@192.168.1.100:554/Src/MediaInput/stream_3`
- Template: main `/Src/MediaInput/stream_1`, sub `/Src/MediaInput/stream_2`, third `/Src/MediaInput/stream_3`
- Source: https://i-pro.com/products_and_solutions/en/media/documentation_file/command-interface-i-pro_h265models

### Panasonic / i-PRO: path 2

Multi-sensor and fisheye quad models, ch 1-4.

- Main stream: `rtsp://admin:password@192.168.1.100:554/Src/MediaInput/stream_1/ch_1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/Src/MediaInput/stream_2/ch_1`
- Template: main `/Src/MediaInput/stream_1/ch_{ch}`, sub `/Src/MediaInput/stream_2/ch_{ch}`
- Source: https://i-pro.com/products_and_solutions/en/media/documentation_file/command-interface-i-pro_h265models

### Panasonic / i-PRO: path 3

Old URL; only when the encoding is H.264.

- Main stream: `rtsp://admin:password@192.168.1.100:554/Src/MediaInput/h264/stream_1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/Src/MediaInput/h264/stream_2`
- Template: main `/Src/MediaInput/h264/stream_1`, sub `/Src/MediaInput/h264/stream_2`
- Source: https://i-pro.com/products_and_solutions/en/media/documentation_file/command-interface-i-pro_h265models

### Panasonic / i-PRO: path 4

Older BL/WV series.

- Main stream: `rtsp://admin:password@192.168.1.100:554/MediaInput/h264`
- Template: main `/MediaInput/h264`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Panasonic BL-C230;WC-S3531L'; maker doc cited by CamioCam: http://security.panasonic.com/support/technical/qr_guide_c230/

### Panasonic / i-PRO: path 5

Older BB-HCM series.

- Main stream: `rtsp://admin:password@192.168.1.100:554/nphMpeg4/nil-640x480`
- Template: main `/nphMpeg4/nil-640x480`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Panasonic BB-HCM531A'

## Pelco RTSP URL

Default port: 554

Example from the Sarix Multi Enhanced manual (u = unicast). The official document says the address can only be seen on the camera web page under A/V Streams and gives no sub stream path, so none is listed. No official source was found for stream1/stream2 paths.

- Main stream: `rtsp://admin:password@192.168.1.100:554/defaultPrimary?streamType=u`
- Template: main `/defaultPrimary?streamType=u`
- Source: https://www.pelco.com/fs/documents/pelco-sarix-multi-enhanced-operationsmanual-en-083023.pdf (C6729M 08/23, pp. 30-31)

## Provision-ISR RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/udp/av0_0`
- Template: main `/udp/av0_0`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Provision-ISR R838'

## Q-See RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/cam/realmonitor?channel=1&subtype=1`
- Template: main `/cam/realmonitor?channel=1&subtype=0`, sub `/cam/realmonitor?channel=1&subtype=1`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Q-See QCW2MPSL'

## Reolink RTSP URL

Default port: 554

Guide: [Reolink RTSP URL and PC viewing](https://litmusnvr.com/reolink-rtsp-url)

### Reolink: path 1

Cameras use 01; NVRs and the Home Hub use the channel number. RTSP is turned off on many models.

- Main stream: `rtsp://admin:password@192.168.1.100:554/Preview_01_main`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/Preview_01_sub`
- Template: main `/Preview_{ch2}_main`, sub `/Preview_{ch2}_sub`
- Source: https://support.reolink.com/articles/900000630706-Introduction-to-RTSP/

### Reolink: path 2

Older format. Not listed on Reolink's official RTSP page.

- Main stream: `rtsp://admin:password@192.168.1.100:554/h264Preview_01_main`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/h264Preview_01_sub`
- Template: main `/h264Preview_{ch2}_main`, sub `/h264Preview_{ch2}_sub`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Reolink RLC-410WS;RLC-423S'; maker doc cited by CamioCam: https://reolink.com/docs/Reolink-Info.pdf

## Revo RTSP URL

Default port: 554

NVR channel.

- Main stream: `rtsp://admin:password@192.168.1.100:554/trackID=1`
- Template: main `/trackID={ch}`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Revo NVR'

## Samsung Techwin (legacy) RTSP URL

Default port: 554

### Samsung Techwin (legacy): path 1

SmartCam SNH series: 5 = 1080p, 4 = 720p, 3 = 360p.

- Main stream: `rtsp://admin:password@192.168.1.100:554/profile5/media.smp`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/profile3/media.smp`
- Third stream: `rtsp://admin:password@192.168.1.100:554/profile4/media.smp`
- Template: main `/profile5/media.smp`, sub `/profile3/media.smp`, third `/profile4/media.smp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Samsung Techwin SNH-E6411BN etc.'; maker doc cited by CamioCam: https://www.samsungsv.com/Download/SNH-P6410BN-User-Manual.pdf

### Samsung Techwin (legacy): path 2

0 main, 1 sub, 2 mobile.

- Main stream: `rtsp://admin:password@192.168.1.100:554/ch01/0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/ch01/1`
- Third stream: `rtsp://admin:password@192.168.1.100:554/ch01/2`
- Template: main `/ch01/0`, sub `/ch01/1`, third `/ch01/2`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Samsung Techwin SNC-4241BE'; maker doc cited by CamioCam: https://www.samsungsv.com/Download/SNK-D5081_User_Manaul.pdf

### Samsung Techwin (legacy): path 3

SDR/SDH DVRs, channels 01-08.

- Main stream: `rtsp://admin:password@192.168.1.100:554/ch01/0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/ch01/1`
- Template: main `/ch{ch2}/0`, sub `/ch{ch2}/1`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Samsung Techwin SDR-B74301'; maker doc cited by CamioCam: https://cdn.shopify.com/s/files/1/0860/0718/files/SDH-B74041_-_User_Manual.pdf

## Sharx Security RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/live/0/h264.sdp`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/live/2/h264.sdp`
- Third stream: `rtsp://admin:password@192.168.1.100:554/live/1/h264.sdp`
- Template: main `/live/0/h264.sdp`, sub `/live/2/h264.sdp`, third `/live/1/h264.sdp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Sharx Security SCNC2900 etc.'

## Sony RTSP URL

Default port: 554

SNC series. Not confirmed in Sony's official documentation.

- Main stream: `rtsp://admin:password@192.168.1.100:554/media/video1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/media/video2`
- Template: main `/media/video1`, sub `/media/video2`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Sony Corporation SNC-EM632R etc.'

## Sricam RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/onvif1`
- Template: main `/onvif1`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Sricam SP-009'

## Swann RTSP URL

Default port: 554

Recorders only (DVR, NVR, SecureAlert, AllSecure, AdvancedX; no documentation for EliteX). Official format rtsp://admin:PW@LAN_IP:554/XY, where X = channel (0 = ch1) and Y = 0 main, 1 sub. The notation for channel 10 and above is not documented. Standalone cameras (SWIFI) do not support RTSP.

- Main stream: `rtsp://admin:password@192.168.1.100:554/00`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/01`
- Template: main `/{ch0}0`, sub `/{ch0}1`
- Source: https://support.swann.com/hc/en-us/articles/60259789314713-Access-Your-Swann-Camera-Using-RTSP

## Techview RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/12`
- Template: main `/12`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Techview Indoor Camera'

## TP-Link Tapo RTSP URL

Default port: 554

Guide: [TP-Link Tapo RTSP URL and PC viewing](https://litmusnvr.com/tapo-rtsp-url)

### TP-Link Tapo: path 1

Requires a camera account created in the Tapo app. Many battery-powered models do not support RTSP.

- Main stream: `rtsp://admin:password@192.168.1.100:554/stream1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/stream2`
- Template: main `/stream1`, sub `/stream2`
- Source: https://www.tp-link.com/us/support/faq/2680/

### TP-Link Tapo: path 2

Second (telephoto) lens on dual-lens models.

- Main stream: `rtsp://admin:password@192.168.1.100:554/stream6`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/stream7`
- Template: main `/stream6`, sub `/stream7`
- Source: https://www.tp-link.com/us/support/faq/2680/

## TP-Link VIGI RTSP URL

Default port: 554

Guide: [TP-Link VIGI RTSP URL and PC viewing](https://litmusnvr.com/vigi-rtsp-url)

### TP-Link VIGI: path 1

Cameras.

- Main stream: `rtsp://admin:password@192.168.1.100:554/stream1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/stream2`
- Template: main `/stream1`, sub `/stream2`
- Source: https://www.tp-link.com/us/support/faq/3718/

### TP-Link VIGI: path 2

NVRs (with the RTSP server enabled). Channels start at 1; 0 is Channel-Zero.

- Main stream: `rtsp://admin:password@192.168.1.100:554/live/1/1/avm`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/live/1/2/avm`
- Template: main `/live/{ch}/1/avm`, sub `/live/{ch}/2/avm`
- Source: https://www.tp-link.com/en/support/faq/4677/

## TRENDnet RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/Streaming/channels/101`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/Streaming/channels/102`
- Template: main `/Streaming/channels/101`, sub `/Streaming/channels/102`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Trendnet IP310PI'; maker doc cited by CamioCam: https://www.trendnet.com/support/supportdetail.asp?prod=190_TV-IP310PI

## TRUEN RTSP URL

Default port: 554

### TRUEN: path 1

Path exactly as written in the official document.

- Main stream: `rtsp://admin:password@192.168.1.100:554/video1+audio1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/video1s1+audio1`
- Third stream: `rtsp://admin:password@192.168.1.100:554/video1s2+audio1`
- Template: main `/video1+audio1`, sub `/video1s1+audio1`, third `/video1s2+audio1`
- Source: https://www.truen.co.kr/customer/technology.php?ptype=view&idx=68&page=1&code=technology

### TRUEN: path 2

TCS-400 and TCS-410 only, channels 1-4.

- Main stream: `rtsp://admin:password@192.168.1.100:554/video1+audio1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/video1s+audio1`
- Template: main `/video{ch}+audio1`, sub `/video{ch}s+audio1`
- Source: https://www.truen.co.kr/customer/technology.php?ptype=view&idx=68&page=1&code=technology

## TVT RTSP URL

Default port: 554

CamioCam lists the main stream only.

- Main stream: `rtsp://admin:password@192.168.1.100:554/?chID=1&streamType=main&linkType=tcp`
- Template: main `/?chID={ch}&streamType=main&linkType=tcp`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'TVT TD2700 Series'; maker doc cited by CamioCam: http://en.tvt.net.cn/upload/products/TD-2700TC-PR%20NV9000%20Quick%20Start%20Guide-450041001028-A0-20170904.pdf

## Tyco Illustra RTSP URL

Default port: 554

- Main stream: `rtsp://admin:password@192.168.1.100:554/ufirststream/ufirststream`
- Template: main `/ufirststream/ufirststream`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Tyco Illustra'

## Ubiquiti UniFi RTSP URL

Default port: 554

### Ubiquiti UniFi: path 1

Frigate brand template (example user name ubnt).

- Main stream: `rtsp://admin:password@192.168.1.100:554/live/ch0`
- Template: main `/live/ch0`
- Source: https://github.com/blakeblackshear/frigate/blob/dev/web/src/types/cameraWizard.ts

### Ubiquiti UniFi: path 2

Older UniFi Video cameras. UniFi Protect uses a token path generated by the app (RTSPS, port 7441), which cannot be looked up from a path list.

- Main stream: `rtsp://admin:password@192.168.1.100:554/s0`
- Template: main `/s0`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Unifi UVC G3'; maker doc cited by CamioCam: https://dl.ubnt.com/guides/unifivideo/UVC-G3_QSG.pdf

## Uniview RTSP URL

Default port: 554

Guide: [Uniview RTSP URL and PC viewing](https://litmusnvr.com/uniview-rtsp-url)

### Uniview: path 1

IP cameras. The second lens uses /media2/video1 to /media2/video3.

- Main stream: `rtsp://admin:password@192.168.1.100:554/media/video1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/media/video2`
- Third stream: `rtsp://admin:password@192.168.1.100:554/media/video3`
- Template: main `/media/video1`, sub `/media/video2`, third `/media/video3`
- Source: https://www.uniview.com/res/202310/26/20231026_1890310_How%20to%20Get%20a%20Uniview%20Camera's%20RTSP%20Stream_974039_168459_0.pdf

### Uniview: path 2

NVRs. The channel number after c is not zero-padded; s0 main, s1 sub.

- Main stream: `rtsp://admin:password@192.168.1.100:554/unicast/c1/s0/live`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/unicast/c1/s1/live`
- Template: main `/unicast/c{ch}/s0/live`, sub `/unicast/c{ch}/s1/live`
- Source: https://www.uniview.com/res/202310/26/20231026_1890323_How%20to%20Get%20the%20URLs%20for%20Uniview%20IPC%20and%20NVR_975509_168459_0.pdf

## Vivotek RTSP URL

Default port: 554

Older firmware. The access name can be changed per stream. Matches the CamioCam CC8130 row.

- Main stream: `rtsp://admin:password@192.168.1.100:554/live.sdp`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/live2.sdp`
- Third stream: `rtsp://admin:password@192.168.1.100:554/live3.sdp`
- Template: main `/live.sdp`, sub `/live2.sdp`, third `/live3.sdp`
- Source: http://download.vivotek.com/downloadfile/downloads/usersmanuals/vs8100-v2manual_en.pdf

## Wansview RTSP URL

Default port: 554

Guide: [Wansview RTSP URL and PC viewing](https://litmusnvr.com/wansview-rtsp-url)

- Main stream: `rtsp://admin:password@192.168.1.100:554/live/ch0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/live/ch1`
- Template: main `/live/ch0`, sub `/live/ch1`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Wansview K3 1080p'

## Zavio RTSP URL

Default port: 554

Profiles 1-4. CamioCam's high/low quality labels (4/1) contradict each other, so the profiles are listed in numeric order. Check on the actual device.

- Main stream: `rtsp://admin:password@192.168.1.100:554/video.pro1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/video.pro2`
- Template: main `/video.pro1`, sub `/video.pro2`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Zavio B8220;B8520'

## Zmodo RTSP URL

Default port: 554

NVR channels 0-3.

- Main stream: `rtsp://admin:password@192.168.1.100:554/tcp/av0_0`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/tcp/av0_1`
- Template: main `/tcp/av{ch0}_0`, sub `/tcp/av{ch0}_1`
- Source: https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv (Apache-2.0) row 'Zmodo NVR'

## Zosi RTSP URL

Default port: 554

Guide: [Zosi RTSP URL and PC viewing](https://litmusnvr.com/zosi-rtsp-url)

### Zosi: path 1

Standalone Wi-Fi cameras.

- Main stream: `rtsp://admin:password@192.168.1.100:554/video1`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/video2`
- Template: main `/video1`, sub `/video2`
- Source: https://supports.zositech.com/hc/en-us/articles/50660190002457-How-to-View-IPC-Camera-Footage-via-RTSP

### Zosi: path 2

PoE cameras.

- Main stream: `rtsp://admin:password@192.168.1.100:554/ucast/11`
- Sub stream: `rtsp://admin:password@192.168.1.100:554/ucast/12`
- Template: main `/ucast/11`, sub `/ucast/12`
- Source: https://supports.zositech.com/hc/en-us/articles/50660190002457-How-to-View-IPC-Camera-Footage-via-RTSP

## Unknown brand — common paths

If the brand is unknown, these brand-independent paths are worth trying (default port 554).

- `rtsp://admin:password@192.168.1.100:554/h264` (The brand-independent paths among the 8 fixed candidates Frigate tries when ONVIF fails). Source: https://github.com/blakeblackshear/frigate/blob/dev/frigate/api/camera.py
- `rtsp://admin:password@192.168.1.100:554/live.sdp`. Source: https://github.com/blakeblackshear/frigate/blob/dev/frigate/api/camera.py
- `rtsp://admin:password@192.168.1.100:554/media.amp`. Source: https://github.com/blakeblackshear/frigate/blob/dev/frigate/api/camera.py
- `rtsp://admin:password@192.168.1.100:554/stream1`. Source: https://github.com/blakeblackshear/frigate/blob/dev/frigate/api/camera.py
- `rtsp://admin:password@192.168.1.100:554/11`. Source: https://github.com/blakeblackshear/frigate/blob/dev/frigate/api/camera.py

## Contributing

Corrections and new brands are welcome. Open an issue or a pull request that includes a link to an official manufacturer source (manual, support article or API document) showing the path. We only accept paths backed by an official source or by a cited dataset under a permissive license. Paths from forums, scanners or unattributed lists are not accepted.

## License

Apache License 2.0. See [LICENSE](LICENSE). Some entries are derived from third-party datasets; see [NOTICE](NOTICE).
