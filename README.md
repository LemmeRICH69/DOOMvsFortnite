# Doom vs Fortnite

Dies ist meine zweite Abgabe der Vorlesung "Game Engines".
Bei dieser Abgabe habe ich folgende Teile in meinem Spiel umgesetzt:

## 1.) Spielmechanik Teil "A. High Mobility"
Ich habe mich für den Aufgabenteil A beim Thema Spielmechanik entschieden. Die dabei geforderten Anforderungen an das Movement wurden alle umgesetzt.
- gesteuert wird mit "W", "A", "S", "D", wobei auch Controller unterstützt sein sollte (hab ich allerdings nicht getestet).
- Durch drücken der Leertaste ist ein normaler Sprung möglich, nach erneutem betätigen in der Luft wird ein Double Jump ausgeführt.
- Mit den Tasten "Q" und "E" kann ein Dash um eine definierte Distanz nach jeweils links und rechts durchgeführt werden.
- Trampoline sind vermehrt auf der Map verteilt.
- Es gibt Steinstrukturen (Ähnlichkeit zu Leitersprossen), an denen ein Spieler hoch/runterklettern kann. Zusätzlich kann man von diesen Leitern nach hinten (dash-ähnlich) abspringen, während man diesen hängt. 
- Den "Grappling Hook" habe ich auf eine bestimmte Weise versucht zu implementieren. Zunächst mal kann man sich in einem bestimmten Radius an alle Objekte (außer andere Spieler) heranziehen. Während des Ziehens kann die Richtung noch leicht durch die Steuerung verändert werden, ist man allerdings zu nah am Endpunkt, ist keine Bewegungssteuerung mehr möglich. Zusätzlich gibt es ein "Katapultier-Feature". Wartet man nicht bis zum Ende sondern löst den "Hook" schon früher, katapultiert sich der Spieler in die gezogene Richtung. Je länger die Distanz zum "Hook" ist, umso stärker ist der Schub, wenn man den "Hook" frühzeitig löst (ist im Video veranschaulicht). Der Nachteil dieses Manövers ist allerdings, dass man solange in diese Richtung weiterfliegt, bis man wieder auf dem Boden steht oder frontal gegen ein Hindernis fliegt.

## 2.) Level mit Probuilder
Hier habe ich versucht eine PvP-Arena zu bauen, in der die Spieler gegeneinander kämpfen können. Die dort verbauten Objekte sollen dazu helfen, das Movement optimal nutzen zu können und vor den Schüssen Deckung zu suchen.

## 3.) Einzel- oder Mehrspieler Teil "B Networking"
Ich hab mich für den Aufgabenteil des Networkings entschieden und mein Spiel durch das PUN2-Netzwerk zum Multiplayerspiel erweitert. Beim Start des Spiels gelangt man ins Lobbymenü, in dem man entweder einen Raum mit selbst definierbarem Namen erstellen, oder mit Hilfe eines Raumnamens einem bestimmten Raum joinen kann. Die Fähigkeiten des Spielers wurden um das Schießen von Bomben und Kugeln erweitert. Dafür wurde eine Waffe eingefügt. Durch wiederholtes Drücken der Taste "F" kann zwischen Kugeln und Bombe gewechselt werden. Dies wird zusätzlich im UI dargestellt. Da Bomben je nach Entfernung zum Spieler deutlich mehr Schaden als Kugeln anrichten, gibt es auf das Schießen von Bomben einen kleinen Cooldown. Stirbt ein Spieler kann er entweder der selben Lobby erneut beitreten, oder zurück in das Lobbymenü gelangen.

## Zusatz
Da ich nicht sonderlich zufrieden mit dem Aussehen der Spieler war (Zylinder aus dem Brackeys Video), musste ich daran etwas ändern. Ich fügte einen Swat-Character von Mixamo hinzu, der nun den Spieler repräsentiert. Zusätzlich ein Animationspack mit "Combat"-Animationen, die ich durch einen Animator eingebunden und über das Netzwerk synchronisiert habe.

Gleichzeitig beschäftigte ich mich daher mit IK, damit die Waffe während den Animationen stetig festgehalten wird. Dazu benutze ich das "Animation Rigging"-Paket von Unity. Leider gibt es manchmal visuelle Glitches in der Animation in Verbindung mit der IK, wo das Model in der FPS-View ganz kurz nicht mehr zu sehen ist. Ich habe diesen Fehler leider nicht mehr in der restlichen Zeit lösen können, wollte aber dennoch das Projekt mit Animation und Character abgeben.


## Benutzte Assets
Die nachfolgenden Assets wurden im Projekt benutzt:

Unity Assets:
- https://assetstore.unity.com/packages/2d/textures-materials/floors/hand-painted-stone-texture-73949
- https://assetstore.unity.com/packages/2d/textures-materials/roads/stone-floor-texture-tile-18683
- https://assetstore.unity.com/packages/2d/textures-materials/brick/18-high-resolution-wall-textures-12567
- https://assetstore.unity.com/packages/2d/textures-materials/stone/stylized-lava-pbr-texture-200039
- https://assetstore.unity.com/packages/3d/props/guns/sci-fi-gun-light-87916
- https://assetstore.unity.com/packages/essentials/asset-packs/standard-assets-for-unity-2018-4-32351
- Animation Rigging -> aus dem package manager

Icons:
- https://www.flaticon.com/de/kostenloses-icon/bombe_112683?term=bomb&page=1&position=4&page=1&position=4&related_id=112683&origin=tag
- https://www.flaticon.com/free-icon/bullet_523764?term=bullet&page=1&position=4&page=1&position=4&related_id=523764&origin=search

Mixamo:
https://www.mixamo.com/#/?page=1&query=Swat&type=Character
https://www.mixamo.com/#/?page=1&query=Pistol%2FHandgun+Locomotion&type=Motion%2CMotionPack

