---
title: 비즈니스용 Skype를 사용 하 여 최신 인증 (ADAL) 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 이 문서에서는 ADAL (Active Directory Authentication Library) 및 OAuth 2.0을 기반으로 하는 최신 인증에 대해 설명 합니다.
ms.openlocfilehash: c984e2468e1735a46c5246806afc57dd67327990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196872"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="07c25-103">비즈니스용 Skype에서 최신 인증 (ADAL)을 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="07c25-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="07c25-104">이 문서에는 비즈니스용 Skype for Business Server 2015 또는 초기 기간에 대해 3 월 2016 누적 업데이트에서 찾을 수 있는 최신 인증 (Active Directory Authentication Library (ADAL) 및 OAuth 2.0에 기반을 둔)이 도입 되었습니다. 비즈니스용 Skype 서버 2019 릴리스.</span><span class="sxs-lookup"><span data-stu-id="07c25-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="07c25-105">ADAL 이란?</span><span class="sxs-lookup"><span data-stu-id="07c25-105">What is ADAL?</span></span>

<span data-ttu-id="07c25-106">ADAL은 ' Active Directory Authentication Library '의 머리글자어 이며, OAuth 2.0와 함께 최신 인증의 underpinning입니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="07c25-107">이 코드 라이브러리는 보안 토큰을 통해 디렉터리의 보안 리소스를 클라이언트 응용 프로그램 (비즈니스용 Skype 등)에서 사용할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="07c25-108">ADAL은 OAuth 2.0와 함께 작동 하 여 여러 가지 인증 및 권한 부여 시나리오 (예: MFA)와 더 많은 유형의 SAML 인증을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="07c25-109">클라이언트 역할을 하는 다양 한 앱에서 최신 인증을 활용 하 여 보안 리소스를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="07c25-110">비즈니스용 Skype Server에서이 기술은 사용자에 게 리소스에 대 한 적절 한 수준의 권한을 부여 하기 위해 온-프레미스 클라이언트와 온-프레미스 서버 사이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="07c25-111">최신 인증 대화 (ADAL 및 OAuth 2.0에 기반 하는)에는 몇 가지 공통 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="07c25-112">리소스 요청을 하는 클라이언트가 있는 경우,이 경우 클라이언트는 비즈니스용 Skype입니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="07c25-113">클라이언트에 게 특정 수준의 액세스 권한이 필요 하며,이 리소스는 디렉터리 서비스에 의해 보호 되며,이 경우 비즈니스용 Skype 서버용 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="07c25-114">OAuth 연결, 즉 사용자에 게 리소스에 대 한 액세스 *권한을 부여* 하는 전용 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="07c25-115">(OAuth는 더 설명적인 이름 ' 서버 대 서버 ' 인증으로 알려져 있으며 일반적으로 S2S로 간략 한 것입니다.)</span><span class="sxs-lookup"><span data-stu-id="07c25-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="07c25-116">ADAL (비즈니스용 Skype Server 인증) 대화에서 비즈니스용 Skype 서버는 ADFS를 통해 통신 합니다 (Windows Server 2012 R2의 ADFS 3.0).</span><span class="sxs-lookup"><span data-stu-id="07c25-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="07c25-117">인증은 일부 다른 Id 공급자 (IdP)를 사용 하 여 발생할 수 있지만, ADFS와 통신 하려면 비즈니스용 Skype 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="07c25-118">비즈니스용 Skype 서버에서 작동 하도록 ADFS를 구성 하지 않은 경우에는 [adfs 설치](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="07c25-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="07c25-119">ADAL은 비즈니스용 Skype Server 2015에 대 한 3 월 2016 누적 업데이트에 포함 되어 있으며, 비즈니스용 Skype에 대 한 3 월 \*\*\*\* 2016 누적 업데이트를 설치 하 고 성공적인 구성을 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="07c25-120">비즈니스용 Skype 서버 2019의 경우 제품의 최초 릴리스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07c25-121">초기 릴리스에서는 온-프레미스 환경의 최신 인증은 관련 된 혼합 Skype 토폴로지가 없는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="07c25-122">예를 들어, 환경이 비즈니스용 Skype 서버용 일 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="07c25-123">이 문장은 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="07c25-124">ADAL에서 사용 하는 명령이 포함 된 ps1 파일을 포함 하는 PowerShell 패키지는 성공적인 구성을 위해 다운로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c25-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="07c25-125">비즈니스용 Skype에서 최신 인증을 구현 하는 방법에 대 한 자세한 내용은 비즈니스용 [skype에서 최신 인증 (ADAL)을 사용 하는 방법](../../manage/authentication/use-adal.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07c25-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
