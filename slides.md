name: dblue
class: bg-dark-blue, center, middle
layout: true

<span class="twitter_id">@leggetter</span>

---

name: green
class: green-template, center, middle
layout: true

<span class="twitter_id">@leggetter</span>

---

name: lblue
layout: true
class: bg-light, center, middle

<span class="twitter_id">@leggetter</span>

---

name: black
layout: true
class: bg-black, center, middle

<span class="twitter_id">@leggetter</span>

---

name: white
layout: true
class: bg-white, center, middle, white-text

<span class="twitter_id">@leggetter</span>

---

template: dblue
class: hide-slide-numbers title

# Easily Integrating Real-Time Communications into Your Web Apps

<img style="vertical-align: middle;" src="./img/devtalks.png" />

## <code>Cluj/11 May 2016/Web/16:10</code>

???

---

template: dblue
class: title

* <span class="speaker">Phil @leggetter</span>
* <span class="speaker-job-title">Head of Developer Relations</span>
* leggetter@nexmo.com
* <span class="speaker-nexmo-logo"></span>

???

* Real-time since 2001
* SDKs
* Apps
* Evangelism

---

template: white
class: bg-contain
background-image: url(./img/nexmo/what-nexmo-offers.png)

???

---

template: dblue
class: bg-dark-blue, h1-big

# Do We Need Real-Time Functionality?

???

* Here are some examples of apps...

---

class: em-text, bg-contain, trans-h, bottom
background-image: url(./img/twitter-notifications.gif)

# Notifications & Activity Streams

???

Notifications

* Something has happened /Changed
* Alert - do something

Activity Streams: 

* a stream of activity: past & new
* synonymous with social apps
  * Twitter, Facebook, Google+
  * News, Sports

---

class: bg-cover, em-text, trans-h, bg-white, bottom
background-image: url(./img/lequipe-football.png)

# Data Visualizations

---

class: bg-video, trans-h, em-text, bottom

# Chat & Bots

<video id="video" autoplay="true" loop="true">
  <source src="./video/tauth_demo.mp4" type="video/mp4">
</video>

--
play_video:

???

* The 101 of realtime
* An interactive experience
* Real-time matters

---

class: bg-white
background-image: url(./img/messaging-apps.png)

---

class: trans-h, bg-cover, bottom
background-image: url(./img/uber.jpg)

# Real-Time Location Tracking

---

class: trans-h, bottom, bg-cover
background-image: url(./img/gdocs-collaboration.png)

# Multi-User Collaboration

???

* Google Apps
* Cloud 9
* TODO: other

---

class: trans-h top
background-image: url(./img/talky-io.png)

## WebRTC Powered AV Chat

---

class: top

<img width="20%" src="./img/facebook.png" />
<img width="20%" src="./img/slack.png" />
<img width="25%" src="./img/google-docs.png" />
<img width="20%" src="./img/uber.png" />

--

# Users expect a real-time UX

--

# Without a real-time UX your app appears broken

---

template: dblue
class: h1-big

# How to Integrate Real-Time into Your Apps

---

class: fixed-width-list

# Code

* [github.com/leggetter/realtime-idea-space](https://github.com/leggetter/realtime-idea-space)

---

template: dblue

# A Standard App

---

class: bg-video, trans-h, em-text, bottom

<video id="video" controls="true">
  <source src="./video/devtalks-cluj-app-intro.mp4" type="video/mp4">
</video>

--
play_video:

---

template: dblue
class: fixed-width-list top

## Make it Real-Time

* Add real-time framework
* Add code to server
* Add code to client
* BOOM!
--

* Using SignalR

---

class: bg-video, trans-h, em-text, bottom

<video id="video" controls="true">
  <source src="./video/devtalks-cluj-signalr.mp4" type="video/mp4">
</video>

--
play_video:

---

class: fixed-width-list top

## Make it Real-Time = Easy

* Add real-time framework
* Add code to server
* Add code to client

---

template: dblue
class: fixed-width-list top

## Everybody can use SMS

* Provision comment phone number for each Idea
* Handle incoming WebHook from Nexmo when SMS is received
* Use SignalR to push comment to UI

---

class: bg-video, trans-h, em-text, bottom

<video id="video" controls="true">
  <source src="./video/devtalks-cluj-sms-comments.mp4" type="video/mp4">
</video>

--
play_video:

---

class: fixed-width-list top

## Everybody can use + **integrate** SMS 

* Provision comment phone number for each Idea
* Handle incoming WebHook from Nexmo when SMS is received
* Use SignalR to push comment to UI

---

class: bottom
background-image: url(./img/realtime-web-stack-tight-integration-self-hosted.png)

### Self Hosted <small>(Tightly Coupled)</small>

???

* Less initial overhead - quick Integration
* As project grows complexity increases
* Updating request/response cycle may impact realtime functionality and vise-versa
* Likely that the web server is handling load of both standard HTTP and realtime i.e. WebSocket, Server-Sent Events, HTTP fallbacks

---

template: green
class: bottom, trans-h
background-image: url(./img/realtime-web-stack-tight-integration-self-hosted-signalr.png)

--

### Self-Hosted: ASP.NET + SignalR <small>(Tightly Coupled)</small>

???

---

## Self-Hosted: ASP.NET + SignalR: Pro & Cons

.left[
**Pros**

* .NET
* Simple integration
* MS Supported
* *jQuery Dependency*
]

.right[
**Cons**

* Tightly coupled
* RMI only
* Self-Scaling
* Scaling (realtime + HTTP)
]

---

class: bottom, trans-h
background-image: url(./img/realtime-web-stack-integration-self-hosted.png)

### Self-Hosted: .NET + Message Queue <small>(Loosely Coupled)</small>

---

class: img-contain top

[![](./img/signalr-standalone.png)](https://code.msdn.microsoft.com/windowsapps/SignalR-self-hosted-in-6ff7e6c3)

---

## Self-Hosted: .NET + Message Queue - Pro & Cons

.left[
**Pros**

* .NET
* Maps well to PubSub
* Loosely coupled
* Could use another runtime
]

.right[
**Cons**

* How does it fit with RMI/SignalR?
* Multiple components
* Self-scaling
* Queue routing questions
* In: HTTP. Out: WebSocket
]

---

template: green
class: bottom, trans-h demo-splash
background-image: url(./img/realtime-web-stack-integration-self-hosted-msgq-faye.png)

--

### Self-Hosted: ASP.NET + Faye<br /><small>(Loosely Coupled)

---

class: wide

## Self-Hosted + Faye: Pros & Cons

.left[
**Pros**

* PubSub
* Connection fallback
* Redis Queue support
* Simple integration
]

.right[
**Cons**

* Multiple languages/runtimes
* You need to scale
]

---

class: fixed-width-list

## Self-Hosted Real-Time options

* **PHP**: ReactPHP, Ratchet, dNode-php, phpDaemon
* **Java**: Netty, Jetty
* **JavaScript (Node.JS)**: Faye, Socket.IO (Engine.IO), Primus.io
* **.NET (C#)**: SignalR, XSockets
* **Python**: Lots of options built on Tornado
* **Ruby**: em-websocket, Faye

???

---

# What about taking the Hosted Real-Time Approach?

* We're already doing this for SMS
* Offload the persistent connections to a service
* Offload scaling...

---

# Hosted Example

* Update the server
* Update the client
* [BOOM!](https://github.com/leggetter/realtime-idea-space/commit/dec8bc33ccb284a548e9840c8e7ed9941c381c17#diff-da24f603ad732afed979f17b603b6efbL24)

---

template: green
class: bottom, trans-h
background-image: url(./img/realtime-web-stack-integration-hosted-pubnub.png)

---

## Hosted - Pros & Cons


.left[
**Pros**

* Simple & powerful
* Instantly scalable
* Managed & dedicated
* Direct integration. No overhead.
]

.right[
**Cons**

* 3rd party reliance
* Difficult to influence functionality
]

???

* Load-balancing connections
* Maintaining state of connections
* Synchronising data between nodes
* Mapping connections to users?
* Dedicated hosted service will offer :
  * Make things easier and faster  
  * Reduce scaling complexities
  * Natural loose coupling via an API
* Where is your value?
  * Features v Infrastructure

---

class: fixed-width-list

## Hosted Real-Time options

* [Ably](https://ably.io)
* [Firebase](https://firebase.com)
* [Fanout](https://fanout.io)
* [PubNub](https://pubnub.com)
* [Pusher](https://pusher.com)
* [Realtime.co](https://realtime.co)
* [Syncano](https://www.syncano.io/)

???

---

class: bg-white, bg-cover trans-h

background-image: url(./img/real-time-tech-choices.gif)

--

## <a style="color:white; text-decoration: none;" href="https://j.mp/realtime-tech-guide">j.mp/realtime-tech-guide</a>

---

class: top

# Users Expect a Real-Time UX

--

## SMS, Webhooks, HTTP Streaming to WebSocket
--

## Voice...
--

## **Easily Integrated**

---

class: fixed-width-list

# Resources

* [Real-time Tech Guide](http://j.mp/realtime-tech-guide)
* [github.com/leggetter/realtime-idea-space](https://github.com/leggetter/realtime-idea-space)
* [Tools, Tips and Techniques for Developing Real-time Apps](https://www.youtube.com/watch?v=KPEcK4zFuyw)
* [Nexmo](https://www.nexmo.com)

---

template: dblue
class: title

## Easily Integrating Real-Time Communications into Your Web Apps

### Questions?

* <span class="speaker">Phil @leggetter</span>
* <span class="speaker-job-title">Head of Developer Relations</span>
* leggetter@nexmo.com
* <span class="speaker-nexmo-logo"></span>
