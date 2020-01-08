---
title: 'Lync Server 2013: Kerberos 인증을 사용하기 위한 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="ad6e3-102">Lync Server 2013의 Kerberos 인증을 사용하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ad6e3-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad6e3-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ad6e3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ad6e3-104">Kerberos 인증을 사용 하도록 설정 하기 전에 모든 필수 구성 및 인프라 준비를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="ad6e3-105">Active Directory 스키마는 Lync Server 2013에 맞게 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="ad6e3-106">Lync Server 2013에 대 한 Active Directory 포리스트 준비가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="ad6e3-107">Lync Server 2013에 대 한 Active Directory 도메인 준비가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="ad6e3-108">중앙 관리 저장소가 성공적으로 설치 되 고 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="ad6e3-109">토폴로지 작성기를 사용 하 여 토폴로지를 만들고 게시 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="ad6e3-110">프런트 엔드 서버, Standard Edition 서버, 디렉터를 비롯 하 여 웹 서비스를 필요로 하는 서버와 역할이 정의 및 배포 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="ad6e3-111">IIS (인터넷 정보 서비스)는 Lync Server 2013에서 웹 서비스를 지원 하기 위해 권장 역할 서비스를 사용 하 여 구성 및 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="ad6e3-112">필수 구성 요소를 충족 한 후에는 웹 서비스에서 배포에 대 한 Kerberos 인증에 사용할 계정을 하나 이상 만들 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="ad6e3-113">최소한 각 배포에 대해 하나의 Kerberos 인증 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="ad6e3-114">그러나 사이트에서 로컬 Kerberos 인증을 제공 하는 각 사이트의 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="ad6e3-115">사이트 당 하나의 Kerberos 인증 계정만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad6e3-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

