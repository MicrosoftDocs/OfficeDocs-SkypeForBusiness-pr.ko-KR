---
title: 'Lync Server 2013: 서브넷을 네트워크 사이트에 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 419c88e32e3a0dd78fdc2503dcc2bb09b2c705ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Lync Server 2013에서 서브넷을 네트워크 사이트에 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

서브넷 정보는 새 세션이 시작 되는 동안 끝점이 있는 네트워크 사이트를 확인 하는 데 사용 되므로 네트워크의 모든 서브넷은 특정 네트워크 사이트와 연결 되어 있어야 합니다. 세션에서 각 당사자의 위치를 알고 있는 경우 advanced Enterprise Voice 기능에서이 정보를 적용 하 여 통화 설정 또는 라우팅 처리 방법을 결정할 수 있습니다.

<div>


> [!IMPORTANT]  
> 배포에 있는 오디오/비디오에 지 서버의 모든 구성 된 공용 IP 주소를 네트워크 구성 설정에 추가 해야 합니다. 이러한 IP 주소는 마스크가 32 인 서브넷으로 추가 됩니다. 연결 된 네트워크 사이트는 해당 하는 구성 된 네트워크 사이트에 해당 합니다. 예를 들어 중앙 사이트 시카고의 A/V에 지 서버에 해당 하는 공용 IP 주소는 NetworkSiteID 시카고입니다. 공용 IP 주소에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">External A/V 방화벽 및 Lync Server 2013에 대 한 포트 요구 사항 결정</A> 을 참조 하십시오.



</div>

<div>


> [!NOTE]  
> 네트워크에 있지만 서브넷과 연결되지 않은 IP 주소 목록 또는 IP 주소가 포함되어 있지만 네트워크 사이트에 연결되지 않은 서브넷 목록을 지정하는 KHI(Key Health Indicator) 알림이 표시됩니다. 이 알림은 8시간 간격으로 한 번만 발생합니다(해당되는 경우). 관련 알림 정보 및 예는 다음과 같습니다.<BR><STRONG>원본:</STRONG> CS 대역폭 정책 서비스 (핵심)<BR><STRONG>이벤트 번호:</STRONG> 36034<BR><STRONG>수준:</STRONG> 2<BR><STRONG>설명:</STRONG> 다음 IP 주소에 대 한 서브넷: &lt;ip 주소&gt; 목록이 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.<BR><STRONG>원인:</STRONG> 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에서 누락 되었거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.<BR><STRONG>해결 방법:</STRONG> IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.<BR>예를 들어 알림에 표시된 IP 주소 목록이 10.121.248.226 및 10.121.249.20을 나타내는 경우 이러한 IP 주소가 서브넷에 연결되지 않았거나, 이러한 IP 주소가 연결된 서브넷이 네트워크 사이트 속해 있지 않습니다. 10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당하는 서브넷인 경우 다음과 같이 이 문제를 해결할 수 있습니다. 
> <OL>
> <LI>
> <P>IP 주소 10.121.248.226이 10.121.248.0/24 서브넷과 연결되고, IP 주소 10.121.249.20이 10.121.249.0/24 서브넷과 연결되어 있는지 확인합니다.</P>
> <LI>
> <P>10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결되어 있는지 확인합니다.</P></LI></OL>



</div>

네트워크 서브넷 사용에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [새-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [설정-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [제거-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> 여러 개의 서브넷을 사용하는 경우에는 CSV(쉼표로 구분된 값) 파일을 사용하여 서브넷을 사이트에 연결하는 것이 좋습니다. CSV 파일에는 <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG> 등과 같은 네 개의 열이 있어야 합니다.



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>관리 셸을 사용하여 서브넷을 네트워크 사이트에 연결하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  **New-CsNetworkSubnet** cmdlet을  실행하여 서브넷과 네트워크 사이트를 연결합니다.
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    예:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    이 예에서는 서브넷 172.11.12.13과 네트워크 사이트 “Chicago” 간 연결이 만들어졌습니다.

3.  토폴로지의 모든 서브넷에 대해 2단계를 반복합니다.

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>CSV 파일을 가져와서 서브넷과 네트워크 사이트를 연결하려면

1.  추가할 모든 서브넷을 포함하는 CSV 파일을 만듭니다. 예를 들어 다음 내용이 포함된 **subnet.csv** 이름의 파일을 만듭니다.
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  다음 cmdlet을 실행 하 여 **서브넷 .csv**를 가져온 다음 Lync Server 관리 저장소에 해당 콘텐츠를 저장 합니다.
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용하여 서브넷과 네트워크 사이트를 연결하려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  **서브넷** 탐색 단추를 클릭합니다.

4.  **새로 만들기**를 클릭합니다.

5.  **새 서브넷** 페이지에서 **서브넷 ID**를 클릭한 다음 네트워크 사이트와 연결할 서브넷에서 정의한 IP 주소 범위에 첫 번째 주소를 입력합니다.

6.  **마스크**를 클릭한 다음 서브넷에 적용할 비트 마스크를 입력합니다.

7.  **네트워크 사이트 ID**를 클릭한 다음 이 서브넷을 추가하고 있는 사이트의 사이트 ID를 선택합니다.
    
    <div>
    

    > [!NOTE]  
    > 네트워크 사이트를 아직 만들지 않은 경우에는 이 목록이 비어 있게 됩니다. 절차에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in The Lync Server 2013</A>을 참조 하십시오. <STRONG>Get-CsNetworkSite</STRONG> cmdlet을 실행하여 배포에 사용할 사이트 ID를 검색할 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.

    
    </div>

8.  경우에 따라 **설명**을 클릭하고 이 서브넷을 설명하는 추가 정보를 입력합니다.

9.  **커밋**을 클릭합니다.

다른 서브넷을 네트워크 사이트에 추가하려면 이러한 단계를 반복합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

