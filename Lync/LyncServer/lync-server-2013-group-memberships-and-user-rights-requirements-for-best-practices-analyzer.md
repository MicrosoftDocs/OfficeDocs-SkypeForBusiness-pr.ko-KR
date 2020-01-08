---
title: 모범 사례 분석기에 대 한 그룹 멤버 자격 및 사용자 권한 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="9e8df-102">Lync Server 2013의 모범 사례 분석기에 대 한 그룹 구성원 자격 및 사용자 권한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e8df-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e8df-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="9e8df-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="9e8df-104">모범 사례 분석기를 성공적으로 실행 하려면 로그온 하는 데 사용 하는 사용자 계정이 로컬 컴퓨터에서 Administrators 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="9e8df-105">또한 환경을 검색 하려면 사용자 계정이 다음 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="9e8df-106">**도메인 관리자**   가 Active Directory 도메인 서비스 정보를 열거 하 고 도메인 컨트롤러와 글로벌 카탈로그 서버의 WMI (Windows Management Instrumentation) 공급자에 게 전화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="9e8df-107">\*\*\*\*   각 Lync server 2013 내부 컴퓨터와 각 Edge 서버에서 WMI (Windows Management Instrumentation) 공급자에 게 전화 하 고 레지스트리에 액세스 하는 데 필요한 관리자</span><span class="sxs-lookup"><span data-stu-id="9e8df-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="9e8df-108">**RTCUniversalReadOnlyAdmins**   전체 또는 위임 읽기 전용 Lync Server 2013 관리 권한</span><span class="sxs-lookup"><span data-stu-id="9e8df-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="9e8df-109">**Exchange 보기 전용 관리자**   또는 위임 된 exchange 보기 에서만 Microsoft exchange 조직의 관리자에 게 모든 권한이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="9e8df-110">사용자 계정에 충분 한 사용자 권한이 없는 경우 다음 두 가지 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="9e8df-111">명령 프롬프트에서 **runas** 명령을 사용 하 여 사용자 권한이 충분 한 계정으로 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="9e8df-112">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="9e8df-113">**Active Directory에 연결** 페이지에서 모범 사례 분석기를 실행 하는 데 사용할 계정에 대 한 자격 증명을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="9e8df-114">**고급 로그인 옵션 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="9e8df-115">Active Directory 도메인 서비스에 연결 하는 데 사용할 수 있는 세 가지 계정 (예: Lync Server 2013 Edge 서버에 연결 하는 경우 1 개, Exchange 서버에 연결 하는 데 하나)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="9e8df-116">이러한 계정을 지정 하지 않으면 모범 사례 분석기를 로그온 하 고 실행 하는 데 사용한 사용자 계정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e8df-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

