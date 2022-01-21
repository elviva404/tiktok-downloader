<p align="center">
<img src="tiktok_downloader/static/tiktok.svg"><br>
<img src="https://img.shields.io/badge/AUTHOR-KRYPTON--BYTE-brightgreen">
</p>

[![Unittest](https://github.com/krypton-byte/tiktok-downloader/actions/workflows/unittest.yml/badge.svg)](https://github.com/krypton-byte/tiktok-downloader/actions/workflows/unittest.yml)

[![Upload to PyPi](https://github.com/krypton-byte/tiktok-downloader/actions/workflows/python-publish.yml/badge.svg?branch=0.1.7&event=release)](https://github.com/krypton-byte/tiktok-downloader/actions/workflows/python-publish.yml)

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)&nbsp;

[![Downloads](https://static.pepy.tech/personalized-badge/tiktok-downloader?period=total&units=none&left_color=black&right_color=orange&left_text=Downloads)](https://pepy.tech/project/tiktok-downloader)&nbsp;[![viitor](https://visitor-badge.glitch.me/badge?page_id=krypton-byte.tiktok-downloader)]()
# install

```bash
> python3 -m pip install tiktok_downloader
> python3 -m pip install git+https://github.com/krypton-byte/tiktok-downloader
```

<ul>
<li><h2> ssstik</h2></li>

```python
>>> from tiktok_downloader import ssstik
>>> ssstik().get_media("url")
[<[type:video]>, <[type:music]>]
>>> ssstik().get_media("url")[0].download("result.mp4")
```

<li><h2> snaptik</h2></li>

```python
>>> from tiktok_downloader import snaptik
>>>snaptik("url").get_media()
[<[type:video]>, <[type:video]>]
>>> snaptik("url").get_media()[0].download("result.mp4")
```
<li><h2> get info </h2></li>

```python
>>> from tiktok_downloader import info_video
>>> info=info_video("url")
>>> info.caption
>>> info.created
>>> info.id
>>> info.music
>>> info.username
>>> info.created
>>> info.signature
>>> info.verified
```
</ul>

# Command line
<ul>
<li>ssstik</li>

```bash
$ python3 -m tiktok_downloader --url=https://www.tiktok.com/@xxxx/video/xxxx --ssstik 2>/dev/null

[
    {
        "type": "video",
        "url": "https://ssstik.io/fe67718b?url=xxxxxx"
    },
    {
        "type": "video",
        "url": "https://v16m.tiktokcdn.com/xxxxxxxx"
    },
    {
        "type": "music",
        "url": "https://sf16-ies-music-sg.tiktokcdn.com/obj/tos-alisg-ve-xxxx/xxxxxx"
    }
]

```

<li>snaptik</li>

```bash
$ python3 -m tiktok_downloader --url=https://www.tiktok.com/@xxxx/video/xxxx --snaptik 2>/dev/null
[
    {
        "type": "video",
        "url": "https://tikcdn.net/file/xxxxxxxx.mp4"
    },
    {
        "type": "video",
        "url": "https://snapsave.info/dl.php?token=xxxxxxxxxxxxxxx"
    }
]

```

<li> post info</li>

```bash
$ python3 -m tiktok_downloader --url=https://www.tiktok.com/@xxxx/video/xxxx --info
{
    "account": {
        "username": "",
        "nickname": "",
        "signatur": "",
        "create": 0,
        "verified": true
    },
    "music": "",
    "caption": "",
    "create": 0,
    "url": "",
    "id": ""
}
```
</ul>

# Run as web

```bash
$ python3 -m tiktok_downloader --host=0.0.0.0 --port=8000 --server
```
## Deploy Heroku
[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/krypton-byte/tiktok-downloader/tree/master)
## Preview
<img src="image/web.png">

## Request API using curl & wget

```bash
$ wget -O result.mp4 $(curl -sG http://127.0.0.1:8000/snaptik -d url=https://vm.tiktok.com/xxxxxxxx/|jq .[0].url -r)
```
## you can direct Download using browser or curl
```
http://127.0.0.1:8000/snaptik?url=https://vm.tiktok.com/xxxxxxxx/&type=embed
```
### Endpoint 
| Name | Endpoint | Status|
|----|---------|--------|
| <a href="https://snaptik.app">Snaptik</a> | /snaptik | ✓
| <a href="https://tikmate.online">Tikmate</a> | /tikmate |✓
| <a href="https://musicaldown.com/">MusicalDown | /mdown|✓
| <a href="https://ssstik.io">ssstik</a> | /ssstik | ✓
| <a href="https://ttdownloader.com/">ttdownloader</a> | /ttdownloader | ✓
| <a href="https://tikdown.org/">tikdown</a> | /tikdown | ✓
# Donasi
<p align="center"><img src="https://svgur.com/i/Vtt.svg">

</p>
<ul><li><a href="https://saweria.co/kryptonbyte">Saweria</a><li><a href="https://wa.me/6283172366463">Whatsapp</a></li><li><a href="https://trakteer.id/krypton-byte-z8vbo">Trakteer</a></li></ul>




# tiktok-downloader Technical Documentation

**Last updated:** 2022-01-21\
_Document generation aided by **Documatic**_

Automatic Documentation

* [Introduction](#introduction)
* [Code Overview](#code-overview)

## Introduction

This is a technical document detailing
        at a high-level
        what tiktok-downloader does, how it operates,
        and how it is built.

The outline of this document was generated
        by **Documatic**.
<!---Documatic-section-group: arch-start--->


## Project Architecture


<!---Documatic-section-group: arch-end--->

<!---Documatic-section-group: helloworld-start--->


## Code Overview

The codebase has a flat structure, with 14 code files.
<!---Documatic-section-helloworld: setup-start--->
The codebase is compatible with Python 3.6 and above, because of f-string 3.6 in tiktok_downloader/mdown.py.
Install requirements with `pip install -r requirements.txt`.

Run `pip install -e .` in top-level directory to install
package in local directory.
Install from pypi with `pip install main`.



<!---Documatic-section-helloworld: setup-end--->
`tiktok_downloader.test`` has a `__main__` entrypoint.


<!---Documatic-section-helloworld: entrypoints-start--->


## Entrypoints

There are 0 source code entrypoints in top-level `__main__`/`__init__` files.


<!---Documatic-section-helloworld: entrypoints-end--->

<!---Documatic-section-group: concept-start--->
## Concepts
<!---Documatic-section-group: concept-end--->

<!---Documatic-section-group: helloworld-end--->

<!---Documatic-section-group: dev-start--->


## Developers
<!---Documatic-section-dev: setup-start--->





<!---Documatic-section-dev: setup-end--->

<!---Documatic-section-dev: ci-start--->
The project uses GitHub Actions for CI/CD.

| CI File | Purpose |
|:----|:----|
| python-publish |  |
| unittest |  |


<!---Documatic-section-dev: ci-end--->

<!---Documatic-section-group: dev-end--->

### **tiktok-downloader/**

<!---Documatic-section-file: tiktok_downloader/decoder.py--->

#### decoder.py


File has 65 lines added and 5 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/server.py--->

#### server.py


File has 260 lines added and 134 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/ssstik.py--->

#### ssstik.py


File has 75 lines added and 15 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/tikmate.py--->

#### tikmate.py


File has 58 lines added and 21 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/snaptik.py--->

#### snaptik.py


File has 58 lines added and 24 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/mdown.py--->

#### mdown.py


File has 58 lines added and 16 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/utils.py--->

#### utils.py


File has 31 lines added and 9 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/scrapper.py--->

#### scrapper.py


File has 186 lines added and 58 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/tikdown.py--->

#### tikdown.py


File has 49 lines added and 0 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/ttdownloader.py--->

#### ttdownloader.py


File has 47 lines added and 0 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.


<!---Documatic-section-file: tiktok_downloader/__main__.py--->

#### __main__.py


File has 151 lines added and 112 lines removed
                in the past 4 weeks. krypton-byte <rosid6434@gmail.com> is the inferred code owner.
