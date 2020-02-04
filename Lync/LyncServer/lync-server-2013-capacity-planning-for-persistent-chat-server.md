---
title: 'Lync Server 2013: 영구 채팅 서버의 용량 계획'
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
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

영구 채팅 서버는 향후 검색 및 검색을 위해 유지할 수 있는 다중 사용자 실시간 채팅을 수행할 수 있습니다. 사용자의 사서함에 저장 된 IM (그룹 인스턴트 메시징)과 달리, 대화 내용이 구성 되어 있지 않으면 영구 채팅 서버 세션이 더 이상 열려 있는 상태로 유지 되 고, 콘텐츠는 서버에 저장 되며, 메시지, 파일, Url, 기타 데이터를 포함 합니다. 진행 중인 대화.

용량 계획은 영구 채팅 서버 배포를 준비 하는 데 중요 한 역할을 합니다. 이 항목에서는 배포에 가장 적합 한 구성을 결정 하는 데 사용할 수 있는 지원 되는 영구 채팅 서버 토폴로지와 용량 계획 표에 대해 자세히 설명 합니다. 또한 사용량이 가장 많은 시간에 더 많은 용량을 필요로 하는 영구 채팅 서버 배포를 최상으로 관리 하는 방법을 설명 합니다.

영구 채팅 서버를 다운로드 하려면 "Microsoft Lync Server 13 영구 채팅 서버"를 참조 [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)하세요.

영구 채팅 서버를 설치 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 설치](lync-server-2013-installing-persistent-chat-server.md) 및 [lync Server 2013의 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server.md) 에서 배포 설명서를 참조 하세요.

Lync Server 계획 도구와 같은 지원 도구는 용량 계획에 대 한 추가 지원을 제공할 수 있습니다. 계획 도구에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하세요.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>영구 채팅 서버 지원 토폴로지

단일 서버 또는 다중 서버 풀에서 영구 채팅 서버를 배포 하 고 단일 풀 또는 다중 풀 토폴로지에 사용할 수 있습니다.

이제 새 Lync Server 2013 배포에 대 한 Standard Edition server의 영구 채팅 서버도 지원 합니다. 그러나 성능 및 확장성에 영향을 줄 수 있으며,이 새로운 배포에 대 한 고가용성 옵션이 없기 때문에 개념 입증, 평가 등의 목적으로이를 주로 사용 하는 것이 좋습니다.

<div>


> [!NOTE]  
> 두 토폴로지에 대 한 자세한 내용은이 설명서의 <A href="lync-server-2013-planning-for-persistent-chat-server.md">Lync server 2013에서 영구</A> 채팅 서버 계획 및 배포 설명서의 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013에서 영구 채팅 서버</A> 설정 및 배포를 참조 하세요.



</div>

<div>

## <a name="single-server-topology"></a>단일 서버 토폴로지

영구 채팅 서버용 최소 구성과 가장 간단한 배포는 단일 영구 채팅 서버 프런트 엔드 서버 토폴로지입니다. 이 배포에는 영구 채팅 서버를 실행 하는 단일 서버 (선택적으로 준수 서비스를 실행 하는 경우), SQL Server 데이터베이스를 모두 호스트 하는 서버, 준수 해야 하는 SQL Server 데이터베이스 등이 필요 합니다. 준수 데이터

<div>


> [!IMPORTANT]  
> 토폴로지 작성기에서 단일 서버 배포로 시작 되는 영구 채팅 서버 풀에는 다른 서버를 추가할 수 없습니다. 단일 서버를 사용 하 고 있는 경우에도 다중 서버 풀 토폴로지를 사용 하는 것이 좋습니다. 따라서 필요한 경우 나중에 서버를 추가할 수 있습니다. 


</div>

다음 그림에는 단일 영구 채팅 서버 프런트 엔드 서버에 대 한 모든 필수 및 선택적 구성 요소 (준수)가 나와 있습니다.

**단일 영구 채팅 서버**

![Compliance Service를 사용하는 단일 서버 토폴로지](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Compliance Service를 사용하는 단일 서버 토폴로지")

</div>

<div>

## <a name="multiple-server-topology"></a>다중 서버 토폴로지

더 나은 용량과 안정성을 제공 하기 위해 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)에서 설명한 대로 다중 서버 토폴로지를 배포할 수 있습니다. 다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 4 대의 활성 컴퓨터가 포함 될 수 있습니다 (고가용성 및 재해 복구 구성은 최대 8 개까지 허용 되지만, 나머지 4 개는 활성 상태로 유지 될 수 있습니다). 각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대에서 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자를 지원 합니다. 다중 서버 토폴로지는 여러 서버에서 영구 채팅 서버를 호스트 하는 것을 제외 하 고 단일 서버 토폴로지와 동일 하며 더 높은 배율을 확장할 수 있습니다. 영구 채팅 서버를 실행 하는 여러 컴퓨터는 Lync Server 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있어야 합니다.

다음 그림은 영구 채팅 서버, 선택적 준수 서비스, 별도 규정 준수 데이터베이스를 실행 하는 여러 컴퓨터가 있는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.

**여러 영구 채팅 서버**

![다중 서버 토폴로지](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "다중 서버 토폴로지")

8만 사용자가 영구 채팅에 동시에 로그인 하 여 사용할 수 있는 4 서버 영구 채팅 서버 배포의 경우 서버 당 2만 사용자가 부하를 균등 하 게 배포 합니다. 한 서버를 사용할 수 없게 되 면 해당 서버에 연결 된 사용자가 영구 채팅 서버에 대 한 액세스 권한을 잃게 됩니다. 연결이 끊긴 사용자는 사용할 수 없는 서버가 복원 될 때까지 자동으로 나머지 서버로 전송 됩니다. 네트워크의 영구 채팅 소통량의 양에 따라,이 전송은 몇 분 정도 걸릴 수 있습니다. 나머지 서버는 각각 3만 사용자를 호스트할 수 있기 때문에 사용 불가능 한 서버를 가능한 한 빨리 복원 하 여 성능 문제를 방지 하는 것이 좋습니다. 그렇지 않으면 토폴로지 작성기 또는 Windows PowerShell cmdlet ( **CsPersistentChatActiveServer)** 을 사용 하 여 다른 영구 채팅 서버를 사용할 수 있습니다.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>영구 채팅 서버 용량 계획

다음 표는 영구 채팅 서버의 용량을 계획 하는 데 도움이 될 수 있습니다. 다양 한 영구 채팅 서버 설정을 변경 하는 방법이 용량 기능에 미치는 영향을 모델링 합니다.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>영구 채팅 서버의 최대 용량 계획

다음 예제 테이블을 사용 하 여 지원할 수 있는 사용자 수를 결정 합니다.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>영구 채팅 서버 풀 최대 용량 샘플

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>활성 영구 채팅 서비스 인스턴스</p></td>
<td><p><em>4(tcp/ipv4)</em></p></td>
</tr>
<tr class="even">
<td><p>영구 채팅 서비스 인스턴스</p></td>
<td><p><em>8 (4는 비활성 이어야 하 고 최대 4 개까지 활성화할 수 있음)</em></p></td>
</tr>
<tr class="odd">
<td><p>활성 사용자가 연결 됨</p></td>
<td><p><em>8만</em></p></td>
</tr>
<tr class="even">
<td><p>프로 비전 된 총 사용자</p></td>
<td><p>15만</p></td>
</tr>
<tr class="odd">
<td><p>끝점 수</p></td>
<td><p>12만</p></td>
</tr>
</tbody>
</table>


앞의 예제에서 계획은 영구 채팅 서버에서 허용 하는 최대 사용자 수 인 영구 채팅 서비스의 네 가지 서버/인스턴스 (고가용성 및 재해 복구용으로 영구 채팅 서버를 실행 하는 4 개 이상의 수동 서버를 포함할 수 있음) 및 서버당 2만 사용자의 총 8만 활성 사용자를 지원 하는 것입니다.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>영구 채팅방 액세스를 관리 하기 위한 용량 계획

다음 예제 표는 영구 채팅 서버 풀에서 영구 채팅방 액세스를 관리 하는 데 도움이 될 수 있습니다.

### <a name="managing-chat-room-access-sample"></a>채팅방 액세스 관리 샘플

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
<th>중간 채팅방</th>
<th>대형 채팅방</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>채팅방 크기 (연결 된 사용자 수)</p></td>
<td><p>회의실 당 30 개</p></td>
<td><p>회의실 당 150</p></td>
<td><p>회의실 당 16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>채팅방</p></td>
<td><p>32000</p></td>
<td><p>1067</p></td>
<td><p>1천만</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>auditorium 된 채팅방 의%</p></td>
<td><p>raid-1</p></td>
<td><p>raid-1</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>열려 있는 채팅방 의%</p></td>
<td><p>3-4</p></td>
<td><p>3-4</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>채팅방 열기 (명시적 멤버쉽 없음)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5mb</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>열지 않은 방 (명시적 구성원 자격이 있는 일반 회의실)</p></td>
<td><p>31040</p></td>
<td><p>1.035</p></td>
<td><p>5mb</p></td>
<td><p>32080</p></td>
</tr>
<tr class="odd">
<td><p>Auditorium 채팅방 (추가 발표자 항목)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5mb</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>직접 회원 들이 관리 하는 채팅방</p></td>
<td><p>50%</p></td>
<td><p>1천만</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>사용자 그룹이 관리 하는 채팅방</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>열려 있는 채팅방의 각 채팅방 구성원 목록에 있는 사용자 그룹 (명시적으로 지정 되지 않음)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>비 열려 있는 채팅방의 각 채팅방 구성원 목록에 있는 사용자</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>비 열려 있는 채팅방의 각 채팅방 구성원 목록에 있는 사용자 그룹</p></td>
<td><p>3</p></td>
<td><p>5mb</p></td>
<td><p>1천만</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>각 채팅방의 관리자 목록에 있는 사용자 및 사용자 그룹 (개방 또는 비 열려 있는 채팅방)</p></td>
<td><p>26</p></td>
<td><p>26</p></td>
<td><p>26</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>각 auditorium 대화방의 발표자 목록에 있는 사용자 및 사용자 그룹 (열기 및 열지 않은 채팅방)</p></td>
<td><p>26</p></td>
<td><p>26</p></td>
<td><p>26</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>열려 있지 않은 모든 채팅방에 걸친 사용자 기반 구성원 자격 엔터티</p></td>
<td><p>465600</p></td>
<td><p>15520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>열려 있지 않은 모든 채팅방에서 사용자 그룹 기반 구성원 자격 엔터티</p></td>
<td><p>46560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>모든 auditorium 채팅방에 걸친 사용자 및 사용자 그룹 기반 엔터티</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모든 채팅방 관리자 목록에서 사용자 및 사용자 그룹 기반 관리자 엔터티</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>채팅방 별 활성 사용자</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>사용자 당 채팅방</p></td>
<td><p><em>까지</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>각 채팅방의 구성원 목록에 있는 사용자 그룹</p></td>
<td><p><em>1천만</em></p></td>
<td><p><em>1천만</em></p></td>
<td><p><em>~</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>사용자 그룹이 관리 하는 채팅방</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>모든 채팅방에 걸친 사용자 그룹 기반 구성원 자격 엔터티</p></td>
<td><p>155200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모든 채팅방에 걸친 사용자 기반 구성원 자격 엔터티</p></td>
<td><p>465600</p></td>
<td><p>77600</p></td>
<td><p>72000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>각 채팅방의 관리자, 발표자 및 범위 목록에 있는 사용자 및 사용자 그룹</p></td>
<td><p>26</p></td>
<td><p>26</p></td>
<td><p>26</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모든 채팅방의 관리자, 발표자 및 범위 목록에 걸친 사용자 및 사용자 그룹</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>액세스 제어 항목</p></td>
<td><p>704160</p></td>
<td><p>26768</p></td>
<td><p>160</p></td>
<td><p>731088</p></td>
</tr>
<tr class="even">
<td><p>최대 액세스 제어 항목</p></td>
<td></td>
<td></td>
<td></td>
<td><p>200만</p></td>
</tr>
</tbody>
</table>


앞의 예제에서 권장 지침에 따라 영구 채팅 서버를 배포 하는 경우 준수가 설정 된 4 개 서버 풀에서 최대 8만 명의 활성 사용자를 처리할 수 있습니다.

이 샘플에서는 작은 (주어진 시간에 30 명의 활성 사용자), 중간 (150 활성 사용자) 및 대규모 (16000 활성 사용자) 채팅방을 표시 합니다. 특정 크기의 채팅방 수는 총 수를 기준으로 계산 됩니다.

  - 시스템의 활성 사용자

  - 지정 된 크기의 채팅방에 있는 활성 사용자

  - 단일 사용자가 참가 하는 지정 된 크기의 채팅방

각 채팅방에 대해 앞의 용량 계획 표는 채팅방에 직접 할당 된 항목을 포함 하 여 채팅방과 연결 된 액세스 제어 항목의 수를 지정 합니다. Acl (액세스 제어 목록)을 사용 하 여 각 채팅방에 대 한 액세스를 제어할 수 있습니다. 범주 수준에서 액세스를 제어할 수도 있습니다. ACL에서 개별 액세스 제어 항목은 사용자 그룹 (예: 보안 그룹, 메일 목록 또는 단일 사용자) 일 수 있습니다. 채팅방 관리자, 발표자 및 구성원에 대 한 액세스 제어 항목을 정의할 수 있습니다.

<div>


> [!IMPORTANT]  
> 채팅방을 관리 하기 위한 전략 계획에서는 허용 되는 총 액세스 제어 항목 수가 200만이 된다는 점에 유의 하세요. 계산 된 액세스 제어 항목이 200만를 초과 하는 경우 서버 성능이 크게 저하 될 수 있습니다. 가능 하면이 문제를 방지 하려면 액세스 제어 항목이 개별 사용자 대신 사용자 그룹 이어야 합니다.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>초대에의 한 채팅방 액세스를 관리 하기 위한 용량 계획

다음 용량 계획 표를 사용 하 여 초대를 보내도록 구성 된 영구 채팅 서버에서 영구 채팅 데이터베이스를 만들고 저장 하는 초대 수를 파악할 수 있습니다. Lync Server 제어판의 **채팅방 범주 설정** 페이지를 사용 하거나 Windows PowerShell Cmdlet 인 **csPersistentChatCategory**를 사용 하 여 범주에 대 한 초대를 관리 합니다. Lync 클라이언트에서 시작 된 채팅방 **관리** 페이지를 사용 하거나 Windows PowerShell Cmdlet 인 **csPersistentChatRoom**를 사용 하 여 채팅방에서 초대를 관리할 수 있습니다 (범주에서 허용 하는 내용에 해당).

다음 표의 예제 데이터는 모든 채팅방의 50%에 대 한 **채팅방 설정** 페이지에서 **초대** 옵션을 **Yes**로 설정 하는 것으로 가정 합니다.

<div>


> [!IMPORTANT]  
> 서버에서 생성 된 초대 수에 대해 계산 된 값이 100만를 초과 하는 경우 서버 성능이 크게 저하 될 수 있습니다. 이 문제를 방지 하려면 초대를 보내도록 구성 된 채팅방 수를 최소화 하거나 초대를 보내도록 구성 된 채팅방에 참가할 수 있는 사용자 수를 제한 해야 합니다.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>초대에의 한 채팅방 액세스 샘플

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
<th>중간 채팅방</th>
<th>대형 채팅방</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>채팅방에 액세스할 수 있는 사용자</p></td>
<td><p>회의실 당 30 개</p></td>
<td><p>회의실 당 150</p></td>
<td><p>회의실 당 16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>초대가 있는 채팅방의 백분율</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>초대를 보낼 수 있도록 구성 된 채팅방</p></td>
<td><p><em>16000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5mb</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>채팅방에 액세스할 수 있는 사용자</p></td>
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
<td><p>허용 되는 최대 초대 수</p></td>
<td></td>
<td></td>
<td></td>
<td><p>200만</p></td>
</tr>
<tr class="odd">
<td><p>모델 1-일일 저장소당 예상 메시지 수로 시작</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>회의실 당 채팅 속도 (일별)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>모든 채팅방의 채팅 속도 (초당)</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>모델 2-하루에 한 사용자에 게 게시 된 메시지 수에 따라 시작</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>일일 사용자 당 채팅 요금</p></td>
<td><p>~</p></td>
<td><p>5mb</p></td>
<td><p>0.1</p></td>
<td><p>명</p></td>
</tr>
<tr class="even">
<td><p>회의실 당 채팅 속도 (일별)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1213</p></td>
</tr>
<tr class="odd">
<td><p>모든 채팅방의 채팅 속도 (초당)</p></td>
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

다음 표에서는 영구 채팅 서버의 사용자 모델에 대해 설명 합니다. 용량 계획 요구 사항에 대 한 기반을 제공 하며, 4 대의 서버에서 8만 동시 사용자를 사용 하는 일반적인 조직을 나타냅니다.

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
<td><p>4(tcp/ipv4)</p></td>
</tr>
<tr class="odd">
<td><p>소량 채팅방의 크기</p></td>
<td><p>사용자 30 명</p></td>
</tr>
<tr class="even">
<td><p>중간 채팅방 크기</p></td>
<td><p>150 사용자</p></td>
</tr>
<tr class="odd">
<td><p>큰 채팅방의 크기</p></td>
<td><p>16000 사용자</p></td>
</tr>
<tr class="even">
<td><p>총 채팅방 수</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>작은 채팅방의 수</p></td>
<td><p>32000</p></td>
</tr>
<tr class="even">
<td><p>중간 채팅방의 수</p></td>
<td><p>1067</p></td>
</tr>
<tr class="odd">
<td><p>대형 채팅방 수</p></td>
<td><p>1천만</p></td>
</tr>
<tr class="even">
<td><p>사용자 당 총 채팅방 수</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>사용자 당 작은 채팅방의 수</p></td>
<td><p>까지</p></td>
</tr>
<tr class="even">
<td><p>사용자 당 중간 채팅방의 수</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>사용자 당 큰 채팅방의 수</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>사용자 당 참가 한 회의실 수</p></td>
<td><p>fps</p></td>
</tr>
<tr class="odd">
<td><p>최고 참여 율</p></td>
<td><p>10/초</p></td>
</tr>
<tr class="even">
<td><p>총 채팅 요금</p></td>
<td><p>24/초</p></td>
</tr>
<tr class="odd">
<td><p>작은 채팅방에 대 한 채팅 요금</p></td>
<td><p>22.22/초</p></td>
</tr>
<tr class="even">
<td><p>중간 채팅방에 대 한 채팅 요금</p></td>
<td><p>1.67/초</p></td>
</tr>
<tr class="odd">
<td><p>대형 채팅방에 대 한 채팅 요금</p></td>
<td><p>~ 0.15/second</p></td>
</tr>
<tr class="even">
<td><p>초대장에 대해 구성 된 채팅방의 백분율</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>직접 회원의 백분율</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>그룹 구성원의 백분율</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 도메인 서비스의 평균 조상 가입 수입니다.</p></td>
<td><p>100-200</p></td>
</tr>
<tr class="even">
<td><p>사용자 당 구독 한 대화 상대 수</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>사용자 당 평균 끝점 수</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>끝점 당 표시 되는 대화방의 평균 수</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>사용자 당 표시 되는 대화방의 평균 수</p></td>
<td><p>2.25 (1 개 채팅방의 경우 50%, 룸의 경우 50%); 각 모니터에 하나씩 최대 6 개의 채팅방을 열 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>간격당 폴링 된 참가자 수</p></td>
<td><p>가시 채팅방 당 25</p></td>
</tr>
<tr class="odd">
<td><p>폴링 간격 길이</p></td>
<td><p>5 분</p></td>
</tr>
<tr class="even">
<td><p>초당 폴링 된 참가자 수</p></td>
<td><p>15000</p></td>
</tr>
<tr class="odd">
<td><p>사용자별 현재 시간 당 변경 수</p></td>
<td><p>26</p></td>
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

