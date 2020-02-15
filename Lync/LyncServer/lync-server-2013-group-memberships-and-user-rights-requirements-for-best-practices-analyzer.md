---
title: 모범 사례 분석기에 대 한 그룹 구성원 자격 및 사용자 권한 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="ed635-102">Lync Server 2013의 모범 사례 분석기에 대 한 그룹 구성원 자격 및 사용자 권한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed635-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed635-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ed635-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ed635-104">모범 사례 분석기를 성공적으로 실행 하려면 로그온 하는 데 사용 하는 사용자 계정이 로컬 컴퓨터에서 Administrators 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="ed635-105">또한 환경을 검색 하려면 사용자 계정이 다음 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="ed635-106">**도메인 관리자**   는 Active Directory 도메인 서비스 정보를 열거 하 고 도메인 컨트롤러 및 글로벌 카탈로그 서버에서 WMI (Windows Management Instrumentation) 공급자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="ed635-107">\*\*\*\*   각 Lync server 2013 내부 컴퓨터와 각에 지 서버에서 WMI (Windows Management Instrumentation) 공급자를 호출 하 고 레지스트리에 액세스 하려면 관리자를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="ed635-108">**RTCUniversalReadOnlyAdmins**   전체 또는 위임 된 읽기 전용 Lync Server 2013 관리 권한</span><span class="sxs-lookup"><span data-stu-id="ed635-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="ed635-109">**Exchange 보기 전용 관리자**   Microsoft exchange 조직에서 전체 또는 위임 된 exchange 보기만 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="ed635-110">사용자 계정에 사용자 권한이 충분 하지 않은 경우 다음과 같은 두 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="ed635-111">명령 프롬프트에서 **runas** 명령을 사용 하 여 사용자 권한이 충분 한 계정으로 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="ed635-112">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="ed635-113">**Active Directory에 연결** 페이지에서 모범 사례 분석기를 실행 하는 데 사용할 계정에 대 한 자격 증명을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="ed635-114">**고급 로그인 옵션 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="ed635-115">Active Directory 도메인 서비스에 연결 하는 데 사용할 수 있는 세 가지 계정, 즉 Lync Server 2013 Edge 서버에 연결 하기 위한 계정과 Exchange 서버에 연결 하는 데 사용할 계정을 각각 하나씩 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="ed635-116">이러한 계정을 지정 하지 않으면 모범 사례 분석기를 로그온 하 고 실행 하는 데 사용한 사용자 계정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed635-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

