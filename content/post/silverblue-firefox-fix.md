---
title: "Воспроизведение mp4-видео в Firefox на Fedora Silverblue"
date: 2019-11-11T16:06:16+05:00
draft: false
---

В Fedora Silverblue 31 Firefox идёт со всеми необходимыми кодеками, чтобы воспроизводить html5-видео, например, на Youtube, но mp4-видео вроде видео, встроенного на Reddit или Twitter, он из коробки не воспроизводит. Быстрый фикс:

1. Установка репозитория RPM Fusion:  
 <code>
 sudo rpm-ostree install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
 </code>

2. Перезагрузка
3. Установка кодеков из RPM Fusion:  
<code>
rpm-ostree install gstreamer1-libav gstreamer1-plugins-bad-free gstreamer1-plugins-bad-free gstreamer1-plugins-bad-free-extras gstreamer1-plugins-bad-freeworld gstreamer1-plugins-bad-nonfree gstreamer1-plugins-good gstreamer1-plugins-ugly lame-libs lame-libs
</code>

4. Перезагрузка.
5. Вместо установки кучи кодеков можно просто установить VLC Player командой:  
<code>
rpm-ostree install vlc
</code>


<!--more-->