---
title: 'Window Managers'
date: '23:28 15-06-2018'
---

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="de">
<head>
	<title>siduction Manuals - Window Managers</title>
	<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
	<style type="text/css" media="all">@import url("../css/content.css");</style>
        <style type="text/css" media="all">@import url("../css/menu.css");</style>
        <style type="text/css" media="print">@import url("../css/print.css");</style>
        <link rel ="shortcut icon" href="../favicon.ico" />
</head>
<!-- Last translation revision by devil 17/01/2012 1800 UTC -->
<body class="body-main">
<div>
<div id="main-page">
	<div class="divider" id="install-add">
			<h2 id="top-header">Einige nützliche Programme, die nicht auf KDE Lite vorhanden sind</h2>

							<p> <span class="highlight-3">Die Aktivierung von non-free in /etc/apt/sources.list.d/debian.list kann notwendig sein</span>.</p>

				<h6>konq-plugins - Plugins für Konqueror. </h6>

							<p>Dieses Paket enthält eine Reihe nützlicher Plugins für Konqueror (Dateimanager, Web-Browser, Dokumentbetrachter). Viele dieser Plugins sind über die Menüleiste zugänglich.</p>
<pre>
apt-get install konq-plugins
</pre>

 							<p>Für den Webbrowser sind hervorzuheben: Übersetzung von Websites, Archivierung von Websites, automatische Aktualisierung, strukturelle Analyse von HTML und CSS, ein Suchfenster, ein Nachrichten-Ticker, Schnellzugang zu oft benutzten Optionen, ein Bookmark-Applet, Schnellzugang zu del.icio.us, Integration in den RSS-Reader aKregator, ein Crashmonitor uvm.</p>

 							<p>Für die Dateiverwaltung sind hervorzuheben: Verzeichnisfilter, Erstellung von Bildgalerien, Erstellung und Extrahierung von gepackten Archiven, schnelles Kopieren und Verschieben, Multimediawiedergabe und Dateiinformationen Dateiinformationen in einer Seitenleiste, graphische Darstellung der Festplattennutzung,  Bildkonvertierung.</p>

				<h6>KDE-Desktopsuche - (Nepomuk und Strigi) </h6>
							<p>KDEs semantische Desktopsuche Nepomuk ist auf einer siduction-kde.iso bereits aktiviert.</p>
 							<p>Die Größe des zur Verfügung gestellten Speicherplatzes und die zu indizierenden Ordner/Dateien kann im Reiter <span class="highlight-3">Erweiterte Einstellungen</span> angepasst werden.</p>

							<p>Der erste Indizierungsdurchlauf kann einige Zeit in Anspruch nehmen. <a href="http://nepomuk.kde.org/"> Mehr Informationen zu Nepomuk (Englisch)</a>. </p>
</div>	
	<div class="divider" id="kde-login">
		<h2>Kein Login in KDE möglich</h2>

							<p>Der Inhalt des <span class="highlight-3">/tmp</span> Verzeichnisses wird normalerweise bei jedem Booten aufgeräumt, sodass auch die für den X-Server notwendigen Verzeichnisse und Sockets gelöscht werden.</p>

							<p>Im normalen Boot-Prozess wird das Skript x11-common aufgerufen und stellt diese Verzeichnisse für XOrg wieder her.</p>

							<p>Möglicherweise wird dieses Skript beim Booten nicht aufgerufen. Man kann die notwendigen Links wieder herstellen:</p>

<pre>
# dpkg-reconfigure x11-common
</pre>
							<p>KDE benötigt für den Anmeldevorgang 5% der Partition, auf der sich /tmp befindet, zum Erstellen der nötigen temporären Dateien. Wenn die Partition zu 95% oder mehr gefüllt ist, kann KDE nicht mehr gestartet werden, und man bekommt nur Zugang zu einer TTY-Konsole.</p>

							<p>Gleiches gilt, falls man eine Endlosschleife des KDM-Anmeldedialogs erhält. Die Lösung ist, in eine TTY-Konsole einzuloggen und das Dateisystem aufzuräumen, nicht benötigte Dateien zu löschen. <i>apt-get clean</i>  bewirkt hier oft Wunder. Es löscht die .debs, die nach dist-upgrades in <i>/var/cache/apt/archives</i> archiviert und allzu leicht vergessen werden </p>

							<p>Alternativ dazu kann eine Desktopumgebung gewählt werden, welche nicht so viele Ressourcen benötigt (<em>fluxbox</em> wird mit siduction ausgeliefert und steht auf einem installierten System zur Verfügung). Auch kann man von der Live-CD/DVD in einem chroot die betroffene Partition aufräumen.</p>

							<p>Empfohlen für den KDE sind mindestens 10% verfügbarer Platz auf der Partition, auf der sich /tmp befindet.</p>

	</div>
	<div class="divider" id="ch-th">
			<h2>Installation von siduction-Graphik und siduction-Themen für KDE</h2>

							<p>Die aktuellen Pakete siduction-art-* können auf diese Weise installiert werden:</p>

<pre>
apt-get install siduction-art-kde-xxxx siduction-art-wallpaper-xxxx
(xxxx ist der Platzhalter für den jeweiligen siduction-Releasenamen, zum Beispiel siduction-art-kde-onestepbeyond)
</pre>
							<p>Damit werden Hintergrundbilder und Themen installiert.</p>

					<h4>Wechsel des Hintergrundbilds:</h4>
							<p><span class="highlight-3">Nach einem Rechtsklick</span> auf den Desktop wählt man  <span class="highlight-3">Einstellungen zum Erscheinungsbild</span>. Unter der Überschrift <span class="highlight-3">Hintergrundbild</span> befindet sich ein Unterpunkt <span class="highlight-3">Bild</span>, der eine Drop-Down-Liste anbietet, aus der man das gewünschte Hintergrundbild wählen kann. Zur Auswahl eines eigenen Bilds befindet sich rechts davon ein "Durchsuchen"-Icon.</p>

					<h4>Änderung des Designs des Anmeldungsmanagers:</h4>
							<p>Um das Design des Anmeldungsmanagers zu ändern, muss zuerst <span class="highlight-3">systemsettings</span> mit Root-Rechten gestartet werden:</p>
<pre>
Alt  + F2 (zum Starten von krunner)
</pre>
<pre>
kdesu systemsettings
</pre>
							<p>Man klickt auf den Reiter <span class="highlight-3">Erweitert</span> und darin auf <span class="highlight-3">Anmeldungsmanager</span>. Dort geht man zum Reiter <span class="highlight-3">Design</span> und wählt das bevorzugte Design. <span class="highlight-3">Das neue Design ist nach dem nächsten Neustart des Computers aktiv</span>.</p>

							<p>Mehr Informationen und Links auf der Seite <a href="http://kde.org">kde.org</a>. </p>
	</div>
	<div class="divider" id="xfce-notes">
			<h2>Nützliche Extras für Xfce</h2>
			</div>
	<div class="divider" id="xfce-notes-1">
			<h3>Installation von siduction-art für Xfce (Wallpapers, Themes)</h3>

							<p>Installation der aktuellen siduction-art auf einem installierten System:</p>

<pre>
apt-get install siduction-art-xfce-xxxx siduction-art-wallpaper-xxxx
(xxxx ist der Release-Name, zum Beispiel: siduction-art-xfce-onestepbeyond)
</pre>

							<p>Damit werden siduction Wallpapers und Themes installiert. Man wählt sie im Anschluss im Einstellungs-Menü von Xfce.</p>

							<p><a href="http://docs.xfce.org/?lang=de">Xfce-Dokumentation (Englisch)</a></p>

							<p><a href="http://wiki.xfce.org/de/start">Xfce wiki (Deutsch)</a></p>
	</div>
	<div class="divider" id="dm">
			  <h2>Sitzungsmanager</h2>
				  <h6>Installation weiterer Desktopumgebungen neben der vorinstallierten:</h6>

							<p>Wenn eine weitere Desktopumgebung neben der aktuellen installiert werden soll (zum Beispiel nach Installation einer siduction-kde.iso möchte man Xfce oder LXDE installieren), wird wahrscheinlich ein Sitzungsmanager mit installiert werden oder der Benutzer installiert selbst einen (GDM, SLIM oder ein anderes *DM-Paket).</p>

							<p>Das Problem ist, dass man nun die Runlevel-Konfiguration von Debian hat. Die Folge ist, man muss vor einer Systemaktualisierung in Runlevel 3 den Grafikserver X manuell beenden.</p>

							<p>Die Lösung ist:</p>
<pre>
apt-get update
apt-get install --reinstall distro-defaults
update-rc.d &lt;dm&gt; remove
update-rc.d &lt;dm&gt; defaults
</pre>
							<p>Beispiele für <span class="highlight-3">update-rc.d &lt;dm&gt; defaults</span> (man beachte den Punkt <span class="highlight-2">.</span> am Ende einer start/stop-Sequenz):</p>

<pre>
update-rc.d kdm start 24 5 . stop 01 0 1 2 3 4 6 .
</pre>

<pre>
update-rc.d gdm start 24 5 . stop 01 0 1 2 3 4 6 .
</pre>

<pre>
update-rc.d slim start 01 5 . stop 01 0 1 2 3 4 6 .
</pre>

	</div>
	<div class="divider" id="desk-freeze">
		<h2>Desktop friert ein</h2>
							<p>Auf keinen Fall direkt zum Resetknopf greifen! Dies könnte das Dateisystem beschädigen und Datenverlust verursachen. In jedem Fall ist das Filesystem nicht sauber nach solch einem harten Reboot (filesystem not clean).</p>

							<p>Wenn nicht einmal mehr ein Wechsel auf ein Terminal, mit <span class="highlight-1">STRG+ALT+F1</span>, oder ein Neustart des X-Servers, mit <span class="highlight-1">strg-alt-backspace</span>, möglich ist, gibt es immer noch Hoffnung:</p>

							<p>Die SysRq-Taste (auf deutschen Tastaturen meistens rechts zu finden und mit "Druck/S-Abf" beschriftet) hilft, ein eingefrorenes System sauber zu rebooten.</p>

							<p> Folgende Sequenz von Tastenkombinationen ist dazu nötig:<br />
							*<span class="highlight-3">  alt+sysrq+r</span> (man gewinnt die kontrolle über die tastatur wieder)<br />
							*<span class="highlight-3">  alt+sysrq+s</span> (führt einen sync aus)<br />
							*<span class="highlight-3">  alt+sysrq+e</span> (sendet term an alle prozesse außer init)<br />
							*<span class="highlight-3">  alt+sysrq+i</span> (sendet kill an alle prozesse außer init)<br />
							*<span class="highlight-3">  alt+sysrq+u</span> (dateisysteme werden read-only gemountet, vermeidet fsck beim neuboot)<br />
							*<span class="highlight-3">  alt+sysrq+b</span> (startet neu. ohne die vorigen schritte käme dies einem hardreset gleich).</p>

							<p>Am besten wartet man nach jedem Schritt einige Sekunden, da z. B. das Beenden der Prozesse schon mal ein bisschen dauern kann. Merken kann man sich die Buchstaben z. B. mit dem Satz "<b><span class="highlight-2">R</span>eboot <span class="highlight-2">S</span>ystem <span class="highlight-2">E</span>ven <span class="highlight-2">I</span>f <span class="highlight-2">U</span>tterly <span class="highlight-2">B</span>roken" </b></p>

							<p>Ein weiterer beliebter Merksatz ist:<br />
							<b> "<span class="highlight-2">R</span>aising <span class="highlight-2">S</span>kinny <span class="highlight-2">E</span>lephants <span class="highlight-2">I</span>s <span class="highlight-2">U</span>tterly <span class="highlight-2">B</span>oring" </b></p>



	</div>

			<div id="rev">Page last revised 17/01/2012 1800 UTC </div>

</div>
</div>
</body>
</html>
