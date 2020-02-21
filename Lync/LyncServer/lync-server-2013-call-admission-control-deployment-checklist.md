---
title: 'Lync Server 2013: 통화 허용 제어 배포 검사 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd1de11f9d169babc8a4367f429d9d99559d6aa6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="99ce5-102">Lync Server 2013에 대 한 통화 허용 제어 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="99ce5-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99ce5-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="99ce5-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="99ce5-104">다음 검사 목록을 사용하여 CAC(통화 허용 제어)를 배포하기 위해 필요한 구성 작업이 모두 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="99ce5-p101">하나 이상의 에지 서버가 배포된 경우 각 외부 인터페이스 IP 주소는 비트 마스크가 32인 네트워크 구성 설정의 서브넷 목록에 추가되어야 합니다. 또한 이 서브넷(IP 주소)을 A/V 에지 서비스가 배포된 지리적 위치의 네트워크 사이트 ID와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99ce5-107">CAC를 구현하는 데 에지 서버는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="99ce5-108">Lync server 제어판을 통해 또는 [Lync server 2013에서 통화 허용 제어 사용](lync-server-2013-enable-call-admission-control.md)에 지정 된 cmdlet을 실행 하 여 CAC를 사용 하도록 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="99ce5-109">CAC가 모든 중앙 사이트에서 사용하도록 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="99ce5-110">토폴로지 작성기를 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="99ce5-111">게시할 때 경고가 표시된 경우 경고를 무시하면 *안 됩니다*.</span><span class="sxs-lookup"><span data-stu-id="99ce5-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="99ce5-112">엔터프라이즈 네트워크에서 관리된 모든 서브넷이 네트워크 구성 설정에서 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="99ce5-113">또한 [Lync Server 2013의 네트워크 사이트에 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)에 설명 된 대로 모든 서브넷을 네트워크 사이트에 연결 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="99ce5-114">모든 프런트 엔드 서버, SBA(Survivable Branch Appliance), 오디오/비디오 회의 서버(별도의 풀에 있는 경우), 중재 서버의 서브넷이나 IP 주소가 네트워크 구성 설정에서 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce5-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

