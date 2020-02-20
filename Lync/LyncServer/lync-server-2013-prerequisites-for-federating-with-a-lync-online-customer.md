---
title: 'Lync Server 2013: Lync Online 고객과의 페더레이션을 위한 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75a6c619b859756151e9d11ee3250d1e4e7bb882
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="02017-102">Lync Server 2013에서 Lync Online 고객과의 페더레이션을 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="02017-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02017-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="02017-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="02017-104">Lync Online 2010 고객에 게 페더레이션 하려면 조직에서 Lync Server 2013의 초기 배포 및 구성을 이미 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02017-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="02017-105">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="02017-105">This includes the following:</span></span>

  - <span data-ttu-id="02017-106">조직에서 하나 이상의 Standard Edition server 또는 Enterprise Edition 프런트 엔드 풀 배포</span><span class="sxs-lookup"><span data-stu-id="02017-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="02017-107">내부 서버를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="02017-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="02017-108">Lync Server 2013에 대해 내부 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02017-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="02017-109">자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013에 대 한 사용자 계정 사용 안 함 또는 다시 사용](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="02017-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="02017-110">외부 사용자 액세스를 지 원하는 데 필요한 하나 이상의에 지 서버 및 다른 구성 요소를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="02017-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="02017-111">자세한 내용은 배포 설명서에서 [페더레이션 및 Lync Server 2013에 대 한 외부 액세스 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="02017-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="02017-112">조직 내에서 페더레이션 지원을 설정하고 페더레이션된 도메인의 액세스를 제어하기 위해 적합한 방법을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="02017-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="02017-113">자세한 내용은 작업 설명서의 lync server [2013에서 조직의 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) 및 [lync server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="02017-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="02017-114">조직의 사용자에 대해 외부 사용자 액세스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02017-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="02017-115">자세한 내용은 [Lync Server 2013의 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) 및 배포 설명서 또는 작업 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="02017-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

