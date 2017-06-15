---
layout: post
comments: true
categories: webrtc
---

* content
{:toc}

Imagine Alice is trying to call Eve. Here's the full offer/answer mechanism in all its gory detail:
1.  Alice creates an RTCPeerConnection object.  
1.  客户端[Alice]创建一个RTCPeerConnection对象  
-  Alice creates an offer (an SDP session description) with the RTCPeerConnection createOffer() method.
-  客户端[Alice]通过RTCPeerConnection.createOffer方法创建一个Offer[^Offer](一个SDP[^SDP]会话描述)
>  Alice calls setLocalDescription() with his offer.
> 客户端[Alice]调用offer上的 setLocalDescription方法
>  Alice stringifies the offer and uses a signaling mechanism to send it to Eve.
> 客户端[Alice]通过信量服务器将Offer[^Offer]发送给客户端[Eve]
>  Eve calls setRemoteDescription() with Alice's offer, so that her RTCPeerConnection knows about Alice's setup.
> 客户端[Eve] 调用RTCPeerConnection上的setRemoteDescription方法设置客户端[Alice]'传过来的Offer[^Offer]
>   Eve calls createAnswer(), and the success callback for this is passed a local session description: Eve's answer.
>   Eve sets her answer as the local description by calling setLocalDescription().
>   Eve then uses the signaling mechanism to send her stringified answer back to Alice.
>   Alice sets Eve's answer as the remote session description using setRemoteDescription().

[^Offer]: 要约
[^SDP]: Session Description Protocol 会话描述协议
