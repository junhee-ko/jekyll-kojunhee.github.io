---
layout: post
title:  "flow, congestion control"
date:   2018-11-21
categories: network
image : https://github.com/KoJunHee/kojunhee.github.io/raw/master/img/networkDoorimg.png
---

flow control은 host와 host 간에 데이터 처리를 효율적으로 하기 위한 방법입니다.

congestion control은 host와 network 간의 데이터 처리를 효율적으로 하기 위한 방법입니다.

## flow control 이란?

송신측과 수신측의 데이터 처리 속도 차이를 해결하기 위한 방법입니다. 

수신측의 데이터 처리 속도가 송신측의 데이터 처리 속도보다 빠르면 문제가 되지 않습니다. 하지만, 송신측의 데

이터 처리 속도가 더 빠르면 문제가 됩니다. 수신측에서 제한된 저장용량을 초과한 이후에 도착하는 데이터는, 손

실 될 수 있으며 만약 손실 된다면 불필요하게 응답과 데이터 전송이 송/수신 측 간에 빈번이 발생합니다. 

이러한 위험을 줄이기 위해 송신 측의 데이터 전송량을 수신측에 따라 조절하는 flow control 이 필요합니다.

stop and wait, sliding window 방식이 있습니다.

## congestion control 이란?

송신측과 네트워크의 데이터 처리 속도 차이를 해결하기 위한 방법입니다.

송신측의 데이터는 지역망이나 인터넷으로 연결된 대형 네트워크를 통해 전달됩니다. 만약 한 라우터에 데이터가 

몰릴 경우, 자신에게 온 데이터를 모두 처리 할 수 없게 됩니다. 이런 경우 호스트들은 또 다시 재전송을 하게되고 

결국 혼잡만 가중시켜 오버플로우나 데이터 손실을 발생시키게 됩니다. 

이러한 네트워크의 혼잡을 피하기 위해 송신측에서 보내는 데이터의 전송 속도를  강제로 줄이는 congestion 

control 이 필요합니다.

AIMD, Slow Start, Fast Transmit, Fast Recovery 방식이 있습니다.