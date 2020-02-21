---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f24d99a8b22c78acd32efdb5867c92a5621fe8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버에 대 한 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

영구 채팅 서버는 향후 검색 및 검색을 위해 유지할 수 있는 여러 사용자 실시간 채팅을 수행할 수 있습니다. 사용자의 사서함에 저장 되는 IM (인스턴트 메시징)과 달리 대화 기록이 구성 되 면 영구 채팅 서버 세션은 더 이상 열어 두고 콘텐츠가 서버에 저장 되며 메시지, 파일, Url 및 기타 데이터를 포함 합니다. 진행 중인 대화입니다.

영구 채팅 서버 배포를 준비 하는 데 있어 용량 계획은 중요 한 역할을 합니다. 이 항목에서는 배포에 가장 적합 한 구성을 결정 하는 데 사용할 수 있는 지원 되는 영구 채팅 서버 토폴로지 및 용량 계획 표에 대해 자세히 설명 합니다. 또한 사용량이 가장 많은 시간에 더 많은 용량을 필요로 하는 영구 채팅 서버 배포를 최상으로 관리 하는 방법을 설명 합니다.

영구 채팅 서버를 다운로드 하려면에서 [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)"Microsoft Lync Server 13영구 채팅 서버"를 참조 하세요.

영구 채팅 서버를 설치 하는 방법에 대 한 자세한 내용은 배포 설명서의 lync [server 2013에서 영구 채팅 서버 설치](lync-server-2013-installing-persistent-chat-server.md) 및 [lync Server 2013의 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server.md) 참조 하십시오.

Lync Server 계획 도구와 같은 지원 도구를 사용 하면 용량을 계획 하는 데 도움이 됩니다. 계획 도구에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하십시오.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>영구 채팅 서버 지원 토폴로지

단일 서버 또는 다중 서버 풀 및 단일 풀 또는 다중 풀 토폴로지에 영구 채팅 서버를 배포할 수 있습니다.

이제 새 Lync Server 2013 배포를 위한 Standard Edition Server의 영구 채팅 서버도 지원 됩니다. 그러나 성능 및 확장성이 영향을 받으며,이 새 배포에 대 한 고가용성 옵션이 없기 때문에 개념 증명, 평가 등의 목적으로이를 주로 사용 하는 것이 좋습니다.

<div>


> [!NOTE]  
> 두 토폴로지에 대 한 자세한 내용은이 문서의 <A href="lync-server-2013-planning-for-persistent-chat-server.md">Lync server 2013에서 영구 채팅 서버 계획</A> 및 배포 설명서의 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013에서 영구 채팅 서버 배포</A> 를 참조 하십시오.



</div>

<div>

## <a name="single-server-topology"></a>단일 서버 토폴로지

영구 채팅 서버에 대 한 최소 구성 및 가장 간단한 배포는 단일 영구 채팅 서버 프런트 엔드 서버 토폴로지입니다. 이 배포를 사용 하려면 영구 채팅 서버를 실행 하는 단일 서버 (선택적으로 준수 서비스를 실행 하는 경우, 준수 기능이 사용 하도록 설정 된 경우), SQL Server 데이터베이스를 모두 호스트 하는 서버 및 준수 해야 하는 경우에는 SQL Server 데이터베이스를 저장 합니다. 준수 데이터

<div>


> [!IMPORTANT]  
> 토폴로지 작성기에서 단일 서버 배포로 시작 된 영구 채팅 서버 풀에는 서버를 더 추가할 수 없습니다. 단일 서버를 사용 하는 경우에도 다중 서버 풀 토폴로지를 사용 하는 것이 좋습니다. 이렇게 하면 나중에 서버를 더 추가할 수 있습니다 (필요한 경우). 


</div>

다음 그림에서는 준수와 함께 단일 영구 채팅 서버 프런트 엔드 서버에 대 한 토폴로지의 모든 필수 및 선택적 구성 요소를 보여 줍니다.

**단일 영구 채팅 서버**

![준수 서비스를 사용 하는 단일 서버 토폴로지](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "준수 서비스를 사용 하는 단일 서버 토폴로지")

</div>

<div>

## <a name="multiple-server-topology"></a>다중 서버 토폴로지

더 많은 용량과 안정성을 제공 하기 위해 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)에 설명 된 대로 다중 서버 토폴로지를 배포할 수 있습니다. 다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 활성 컴퓨터가 최대 4 개까지 포함 될 수 있습니다 (고가용성 및 재해 복구 구성의 경우 8 개까지 가능 하지만 4 개만 활성화 될 수 있으며 나머지 4 개는 대기 중에 있음). 각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대와 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자에 게 해당 합니다. 다중 서버 토폴로지는 다중 서버가 영구 채팅 서버를 호스트 하는 것을 제외 하 고는 단일 서버 토폴로지와 동일 하며 더 높은 규모를 높일 수 있습니다. 영구 채팅 서버를 실행 하는 여러 컴퓨터가 Lync Server 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있어야 합니다.

다음 그림에서는 영구 채팅 서버, 선택적 준수 서비스 및 별도의 준수 데이터베이스를 실행 하는 여러 컴퓨터를 사용 하는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.

**여러 영구 채팅 서버**

![다중 서버 토폴로지](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "다중 서버 토폴로지")

5 대의 서버 영구 채팅 서버 배포에서 8만 사용자가 동시에 영구 채팅에 로그인 하 여 사용할 수 있는 경우 부하는 서버당 2만 사용자에 게 균등 하 게 분산 됩니다. 한 서버를 사용할 수 없는 경우 해당 서버에 연결 된 사용자는 영구 채팅 서버에 대 한 액세스 권한을 잃게 됩니다. 연결이 끊긴 사용자는 해당 서버가 복원될 때까지 나머지 서버로 자동으로 전송됩니다. 네트워크의 영구 채팅 트래픽 양에 따라이 전송에 몇 분 이상 걸릴 수 있습니다. 나머지 각 서버가 3만 명의 사용자를 호스트 하는 경우에는 가능한 한 빨리 사용할 수 없는 서버를 복원 하 여 성능 문제가 발생 하지 않도록 하는 것이 좋습니다. 그렇지 않으면 토폴로지 작성기 또는 Windows PowerShell cmdlet ( **set-cspersistentchatactiveserver)** 을 사용 하 여 다른 영구 채팅 서버를 사용 하도록 설정할 수 있습니다.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>영구 채팅 서버 용량 계획

다음 표에서는 영구 채팅 서버에 대 한 용량 계획을 세울 수 있습니다. 다양 한 영구 채팅 서버 설정이 용량 기능에 미치는 영향을 모델링 합니다.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>영구 채팅 서버에 대 한 최대 용량 계획

다음 샘플 표를 사용하여 지원할 사용자 수를 결정할 수 있습니다.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>영구 채팅 서버 풀 최대 용량 샘플

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>활성 영구 채팅 서비스 인스턴스</p></td>
<td><p><em>1-4</em></p></td>
</tr>
<tr class="even">
<td><p>영구 채팅 서비스 인스턴스</p></td>
<td><p><em>8 (4는 비활성 이어야 하 고 최대 4 개만 활성화할 수 있음)</em></p></td>
</tr>
<tr class="odd">
<td><p>활성 사용자 연결 됨</p></td>
<td><p><em>8만</em></p></td>
</tr>
<tr class="even">
<td><p>총 프로 비전 된 사용자</p></td>
<td><p>15만</p></td>
</tr>
<tr class="odd">
<td><p>끝점 수</p></td>
<td><p>12만</p></td>
</tr>
</tbody>
</table>


앞의 예제에서이 계획은 영구 채팅 서버에서 허용 하는 최대 사용자 수를 지원 하 고, 영구 채팅 서비스의 서버/인스턴스 (고가용성 및 재해 복구를 위해 영구 채팅 서버를 실행 하는 수동 서버가 4 개 이상 있을 수 있음) 및 서버당 사용자 2만 명에 게 총 8만 활성 사용자를 지 원하는 것입니다.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>영구 대화방 액세스 관리를 위한 용량 계획

다음 예제 테이블은 영구 채팅 서버 풀에서 영구 대화방 액세스 관리를 계획 하는 데 도움이 될 수 있습니다.

### <a name="managing-chat-room-access-sample"></a>대화방 액세스 관리 샘플

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>작은 채팅방</th>
<th>중간 대화방</th>
<th>큰 대화방</th>
<th>합계</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>대화방 크기 (연결 된 사용자 수)</p></td>
<td><p>대화방 당 30 개</p></td>
<td><p>대화방 당 150</p></td>
<td><p>대화방 당 16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>대화방 수</p></td>
<td><p>32000</p></td>
<td><p>1067</p></td>
<td><p>10 </p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>강당 인 대화방의 비율입니다.</p></td>
<td><p>개</p></td>
<td><p>개</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>열린 대화방 의%</p></td>
<td><p>3(sp3)</p></td>
<td><p>3(sp3)</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>대화방 열기 (명시적 멤버 자격 없음)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>2-5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>열려 있지 않은 대화방 (명시적 구성원이 있는 일반 대화방)</p></td>
<td><p>31040</p></td>
<td><p>1.035</p></td>
<td><p>2-5</p></td>
<td><p>32080</p></td>
</tr>
<tr class="odd">
<td><p>강당 대화방 (추가 발표자 항목)</p></td>
<td><p>개</p></td>
<td><p>32</p></td>
<td><p>2-5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>직접 멤버 자격이 관리 하는 대화방</p></td>
<td><p>50%</p></td>
<td><p>10</p></td>
<td><p>개</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>사용자 그룹에서 관리하는 대화방 수</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>열려 있는 대화방에 대 한 각 대화방의 구성원 목록에 있는 사용자 그룹 (명시적으로 지정 되지 않음)</p></td>
<td><p>개</p></td>
<td><p>개</p></td>
<td><p>개</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>열려 있지 않은 채팅방에 대 한 각 대화방의 구성원 목록 사용자</p></td>
<td><p>kb</p></td>
<td><p>150</p></td>
<td><p>16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>열려 있지 않은 대화방에 대 한 각 대화방의 구성원 목록에 있는 사용자 그룹</p></td>
<td><p>3(sp3)</p></td>
<td><p>2-5</p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>각 대화방의 관리자 목록에 있는 사용자 및 사용자 그룹 (개방 된 채팅방의 경우)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>각 강당 대화방의 발표자 목록에 있는 사용자 및 사용자 그룹 (개방 된 채팅방 용)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>열려 있지 않은 모든 대화방의 사용자 기반 구성원 엔터티</p></td>
<td><p>465600</p></td>
<td><p>15520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>열려 있지 않은 모든 대화방의 사용자 그룹 기반 구성원 엔터티</p></td>
<td><p>46560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>모든 강당 대화방에서 사용자 및 사용자 그룹 기반 엔터티</p></td>
<td><p>개</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모든 대화방 관리자 목록에서 사용자 및 사용자 그룹 기반 관리자 엔터티</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>대화방당 활성 사용자 수</p></td>
<td><p><em>kb</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>사용자당 대화방 수</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>~</em></p></td>
</tr>
<tr class="odd">
<td><p>각 대화방의 구성원 목록에 있는 사용자 그룹 수</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>f</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>사용자 그룹에서 관리하는 대화방 수</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>모든 대화방의 사용자 그룹 기반 구성원 엔터티 수</p></td>
<td><p>155200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모든 대화방의 사용자 기반 구성원 엔터티 수</p></td>
<td><p>465600</p></td>
<td><p>77600</p></td>
<td><p>72000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>각 대화방의 관리자, 발표자 및 범위 목록에 있는 사용자 및 사용자 그룹 수</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모든 대화방의 관리자, 발표자 및 범위 목록에 있는 사용자 및 사용자 그룹</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>액세스 제어 항목 수</p></td>
<td><p>704160</p></td>
<td><p>26768</p></td>
<td><p>160</p></td>
<td><p>731088</p></td>
</tr>
<tr class="even">
<td><p>최대 액세스 제어 항목 수</p></td>
<td></td>
<td></td>
<td></td>
<td><p>200만</p></td>
</tr>
</tbody>
</table>


위의 예제에서 권장 지침에 따라 영구 채팅 서버를 배포 하는 경우 준수를 사용 하도록 설정 된 4 대의 서버 풀에서 최대 8만 명의 활성 사용자를 처리할 수 있습니다.

이 샘플은 작은 대화방 (지정 된 시간에 30 명의 활성 사용자), 보통 (150 활성 사용자) 및 대규모 (16000 활성 사용자)으로 분류 된 채팅방을 표시 합니다. 특정 크기의 대화방 수는 다음 항목의 합계를 기반으로 계산됩니다.

  - 시스템의 활성 사용자 수

  - 지정된 크기의 대화방에 있는 활성 사용자 수

  - 단일 사용자가 참가하는 지정된 크기의 대화방 수

각 대화방에 대해 이전 용량 계획 테이블은 대화방에 직접 할당 된 항목을 포함 하 여 대화방과 연결 된 액세스 제어 항목 수를 지정 합니다. ACL(액세스 제어 목록)을 사용하여 개별 대화방에 대한 액세스를 제어할 수 있습니다. 또한 범주 수준에서 액세스를 제어할 수 있습니다. ACL에서 개별 액세스 제어 항목은 사용자 그룹 (예: 보안 그룹, 메일 목록 또는 단일 사용자)이 될 수 있습니다. 대화방 관리자, 발표자 및 구성원에 대한 액세스 제어 항목을 정의할 수 있습니다.

<div>


> [!IMPORTANT]  
> 채팅방을 관리 하기 위한 전략을 계획할 때 허용 되는 총 액세스 제어 항목 수가 200만 이라는 점을 염두에 두어야 합니다. 계산 된 액세스 제어 항목이 200만를 초과 하면 서버 성능이 크게 저하 될 수 있습니다. 가능한 경우이 문제를 방지 하려면 액세스 제어 항목이 개별 사용자가 아닌 사용자 그룹 이어야 합니다.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>초대에 의한 대화방 액세스 관리를 위한 용량 계획

다음 용량 계획 표를 사용 하 여 영구 채팅 서버가 초대를 보내도록 구성 된 경우 영구 채팅 데이터베이스에서 만들고 저장 하는 초대 수를 파악할 수 있습니다. 범주에 대 한 초대는 Lync Server 제어판의 **채팅방 범주 설정** 페이지를 사용 하거나, Windows PowerShell cmdlet **get-cspersistentchatcategory**를 사용 하 여 관리 합니다. Lync 클라이언트에서 시작 된 **대화방 관리** 페이지를 사용 하거나 Windows PowerShell cmdlet **clear-cspersistentchatroom**를 사용 하 여 대화방 (범주에서 허용 하는 것과 같은 채팅방)에서 초대를 관리할 수 있습니다.

다음 표의 예제 데이터에서는 대화방 **설정** 페이지에서 모든 대화방의 50%에 대 한 **초대** 옵션을 **' 예 '** 로 설정 하는 것으로 가정 합니다.

<div>


> [!IMPORTANT]  
> 서버에서 생성 하는 초대 수에 대해 계산 된 값이 100만를 초과 하면 서버 성능이 크게 저하 될 수 있습니다. 이 문제를 방지 하려면 초대를 보내도록 구성 된 대화방 수를 최소화 하거나 초대를 보내도록 구성 된 대화방에 참가할 수 있는 사용자 수를 제한 해야 합니다.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>초대에 의한 대화방 액세스 샘플

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>작은 채팅방</th>
<th>중간 대화방</th>
<th>큰 대화방</th>
<th>합계</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>대화방에 액세스할 수 있는 사용자</p></td>
<td><p>대화방 당 30 개</p></td>
<td><p>대화방 당 150</p></td>
<td><p>대화방 당 16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>초대가 있는 대화방의 비율입니다.</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>초대를 보내도록 구성된 대화방 수</p></td>
<td><p><em>16000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>2-5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>대화방에 액세스할 수 있는 사용자 수</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>영구 채팅 서버에서 생성 된 초대</p></td>
<td><p>96만</p></td>
<td><p>12만</p></td>
<td><p>8만</p></td>
<td><p>116만</p></td>
</tr>
<tr class="even">
<td><p>허용되는 최대 초대 수</p></td>
<td></td>
<td></td>
<td></td>
<td><p>200만</p></td>
</tr>
<tr class="odd">
<td><p>모델 1-일별 초당 예상 메시지 수로 시작</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>대화방 당 채팅 속도 (일별)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>모든 대화방에서의 초당 채팅 속도입니다.</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>모델 2-사용자 당 하루에 게시 된 메시지 수에 따라 시작</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>일별 사용자 당 채팅 속도</p></td>
<td><p>15 </p></td>
<td><p>2-5</p></td>
<td><p>0.1</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="even">
<td><p>대화방 당 채팅 속도 (일별)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1213</p></td>
</tr>
<tr class="odd">
<td><p>모든 대화방에서의 초당 채팅 속도입니다.</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>영구 채팅 서버 성능 사용자 모델

다음 표에서는 영구 채팅 서버에 대 한 사용자 모델을 설명 합니다. 용량 계획 요구 사항에 대 한 기반을 제공 하며, 4 대의 서버에서 동시 사용자 8만을 사용 하는 일반적인 조직을 나타냅니다.

### <a name="persistent-chat-server-performance-user-model"></a>영구 채팅 서버 성능 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>연결 된 활성 사용자 수</p></td>
<td><p>8만</p></td>
</tr>
<tr class="even">
<td><p>영구 채팅 서버 서비스 인스턴스 수</p></td>
<td><p>1-4</p></td>
</tr>
<tr class="odd">
<td><p>소규모 대화방의 크기</p></td>
<td><p>사용자 30명</p></td>
</tr>
<tr class="even">
<td><p>중규모 대화방의 크기</p></td>
<td><p>사용자 150명</p></td>
</tr>
<tr class="odd">
<td><p>대규모 대화방의 크기</p></td>
<td><p>16000 사용자</p></td>
</tr>
<tr class="even">
<td><p>총 대화방 수</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>소규모 대화방 수</p></td>
<td><p>32000</p></td>
</tr>
<tr class="even">
<td><p>중규모 대화방 수</p></td>
<td><p>1067</p></td>
</tr>
<tr class="odd">
<td><p>대규모 대화방 수</p></td>
<td><p>10 </p></td>
</tr>
<tr class="even">
<td><p>사용자당 총 대화방 수</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>사용자당 소규모 대화방 수</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>사용자당 중규모 대화방 수</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>사용자당 대규모 대화방 수</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>사용자 당 가입 된 대화방 수</p></td>
<td><p>mb</p></td>
</tr>
<tr class="odd">
<td><p>최대 참가 비율</p></td>
<td><p>10/초</p></td>
</tr>
<tr class="even">
<td><p>총 채팅 비율</p></td>
<td><p>24/초</p></td>
</tr>
<tr class="odd">
<td><p>소규모 대화방의 채팅 비율</p></td>
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>중규모 대화방의 채팅 비율</p></td>
<td><p>1.67/second</p></td>
</tr>
<tr class="odd">
<td><p>대규모 대화방의 채팅 비율</p></td>
<td><p>~ 0.15/second</p></td>
</tr>
<tr class="even">
<td><p>초대에 대해 구성된 대화방의 비율</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>직접 구성원의 비율</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>그룹 구성원의 비율</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 도메인 서비스의 평균 상위 항목 수</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>사용자당 등록된 대화 상대 수</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>사용자 당 평균 끝점 수</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>끝점 당 표시 되는 평균 대화방 수</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>사용자 당 표시 되는 평균 대화방 수</p></td>
<td><p>2.25 (1 개의 채팅방에 50%를, 2 채팅방의 경우 50%); 모니터 마다 하나씩 최대 6 개의 채팅방이 열려 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>간격당 폴링되는 참가자 수</p></td>
<td><p>가시 대화방 당 25 개</p></td>
</tr>
<tr class="odd">
<td><p>폴링 간격</p></td>
<td><p>5분</p></td>
</tr>
<tr class="even">
<td><p>초당당 폴링되는 참가자 수</p></td>
<td><p>15000</p></td>
</tr>
<tr class="odd">
<td><p>사용자별 시간당 현재 상태 변경 수</p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>초당 현재 상태 변경 수</p></td>
<td><p>133.33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

