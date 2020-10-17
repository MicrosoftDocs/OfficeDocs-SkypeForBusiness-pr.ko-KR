---
title: 'Lync Server 2013: 환경 테스트 문제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 812796be0589342f346cfc6755ace64cb402f63a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514085"
---
# <a name="issues-with-the-environment-test-in-lync-server-2013"></a><span data-ttu-id="1a596-102">Lync Server 2013의 환경 테스트 관련 문제</span><span class="sxs-lookup"><span data-stu-id="1a596-102">Issues with the environment test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a596-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1a596-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1a596-104">모범 사례 분석기는 Lync Server 2013 환경이 지원 되는 구성 인지 확인할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-104">Best Practices Analyzer provides a way for you to verify that your Lync Server 2013 environment is a supported configuration.</span></span> <span data-ttu-id="1a596-105">모범 사례 분석기는 Active Directory 도메인 서비스 검사의 일부로서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-105">As part of the Active Directory Domain Services check, Best Practices Analyzer does the following:</span></span>

  - <span data-ttu-id="1a596-106">Active Directory 도메인 서비스 포리스트 및 스키마 준비 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-106">Verifies the Active Directory Domain Services forest and schema preparation.</span></span>

  - <span data-ttu-id="1a596-107">배포에서 Active Directory 도메인 서비스 사이트 및 도메인 수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-107">Identifies the number of Active Directory Domain Services sites and domains in the deployment.</span></span>

  - <span data-ttu-id="1a596-108">포리스트 및 도메인 수준을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-108">Checks the forest and domain levels.</span></span>

  - <span data-ttu-id="1a596-109">도메인 컨트롤러 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-109">Checks the domain controller version.</span></span>

  - <span data-ttu-id="1a596-110">도메인, 구성 및 스키마 명명 컨텍스트를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-110">Identifies the domain, configuration, and schema naming context.</span></span>

  - <span data-ttu-id="1a596-111">활성화된 사용자 수를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-111">Identifies the number of enabled users.</span></span>

  - <span data-ttu-id="1a596-112">전역 Active Directory 도메인 서비스 설정이 저장된 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-112">Checks where the global Active Directory Domain Services settings are stored.</span></span>

  - <span data-ttu-id="1a596-113">Lync Server에 대 한 Scp (서비스 연결 지점)를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-113">Checks for the service connection points (SCPs) for Lync Server.</span></span>

  - <span data-ttu-id="1a596-114">데이터베이스 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-114">Identifies the database version.</span></span>

<div>

## <a name="resolving-issues-with-the-environment"></a><span data-ttu-id="1a596-115">환경 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1a596-115">Resolving Issues with the Environment</span></span>

<span data-ttu-id="1a596-p102">환경 테스트 시 환경 관련 문제가 발견된 경우 대개 Active Directory 구성이나 특정 서버에서 실행 중인 소프트웨어 수준과 관련된 문제가 원인입니다. 예를 들어 모범 사례 분석기를 통해 환경에서 Windows Server 2000을 실행 중인 도메인 컨트롤러가 식별되는 경우 이로 인해 경고가 발생하며 이러한 도메인 컨트롤러를 지원되는 Windows Server로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a596-p102">If the environment test found problems with your environment, these problems are probably caused by issues with your Active Directory configuration or the level of software running on specific servers. For example, if Best Practices Analyzer identifies any domain controllers in your environment that are running Windows Server 2000, it will issue a warning and you will need to upgrade those domain controllers to a supported version of Windows Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

