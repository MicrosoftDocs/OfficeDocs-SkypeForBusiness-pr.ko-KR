---
title: Lync Server 2013 클라이언트 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="1237f-102">Lync Server 2013 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="1237f-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1237f-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1237f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1237f-104">사용자를 Lync Server 2013로 마이그레이션한 후 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="1237f-105">새 Lync Server 2013 서버에서 클라이언트 버전 필터를 사용 하 여 로그인 하는 데 최신 업데이트가 설치 된 클라이언트만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="1237f-106">필요한 경우 클라이언트 부트스트랩에 필요한 그룹 정책 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="1237f-107">자세한 내용은 배포 설명서의 [Lync Server 2013에서 클라이언트 부트스트랩 정책 구성을](lync-server-2013-configuring-client-bootstrapping-policies.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1237f-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="1237f-108">이러한 설정의 구성은 기존 클라이언트 부트스트랩 정책을 변경 하거나 새 클라이언트 부트스트랩 정책을 설정 하려는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="1237f-109">클라이언트 부트스트랩 정책을 구성 하지 않으려는 경우 또는 레거시 클라이언트 부트스트랩 정책을 적용 하려면 아무런 작업도 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="1237f-110">Lync Server 2013 제어판, Lync Server 2013 관리 셸 또는 둘 다를 사용 하 여 특정 사용자 또는 사용자 그룹에 대 한 다른 사용자 및 클라이언트 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="1237f-111">자세한 내용은 계획 설명서의 [Lync 2013에 대 한 새로운 설정 및 변경 설정을](lync-server-2013-new-and-changed-settings-for-lync-2013.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1237f-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="1237f-112">최신 누적 업데이트와 함께 최신 버전의 Lync Server 2013 클라이언트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="1237f-113">자세한 내용은 배포 설명서의 [Lync Server 2013에서 클라이언트 및 장치 배포](lync-server-2013-deploying-clients-and-devices.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1237f-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="1237f-114">) 조직에서 Lync Server 2013 향상 된 현재 상태 개인 정보 모드를 필요로 하는 경우 마이그레이션이 완료 된 후 클라이언트 버전 정책 규칙을 정의 하 여 이전 클라이언트 버전이 로그인 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="1237f-115">그런 다음 향상 된 현재 상태 개인 정보 모드를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1237f-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1237f-116">특정 서버 풀의 모든 사용자가 최신 클라이언트 버전을 설치할 때까지 Lync 2013 향상 된 현재 상태 개인 정보 모드를 사용 하도록 설정 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1237f-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

