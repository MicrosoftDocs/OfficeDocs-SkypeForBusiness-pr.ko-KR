---
title: 비즈니스용 Skype를 사용한 ADAL (최신 인증) 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 이 문서에서는 ADAL (Active Directory 인증 라이브러리) 및 OAuth 2.0을 기반으로 하는 최신 인증에 대해 설명 합니다.
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046291"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="a4040-103">비즈니스용 Skype에서 ADAL (최신 인증)을 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a4040-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="a4040-104">이 문서에서는 비즈니스용 skype 서버 2015 또는 초기에 비즈니스용 Skype 용 2016 누적 업데이트에서 찾을 수 있는 최신 인증 (ADAL (Active Directory 인증 라이브러리) 및 OAuth 2.0을 기반으로 하는)을 소개 합니다. 비즈니스용 Skype 서버 2019에 대 한 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="a4040-105">ADAL 이란?</span><span class="sxs-lookup"><span data-stu-id="a4040-105">What is ADAL?</span></span>

<span data-ttu-id="a4040-106">ADAL은 ' Active Directory Authentication Library '의 머리글자어 이며, OAuth 2.0와 함께 최신 인증의 underpinning입니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="a4040-107">이 코드 라이브러리는 보안 토큰을 통해 클라이언트 응용 프로그램 (예: 비즈니스용 Skype)에서 디렉터리의 보안 리소스를 사용할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="a4040-108">ADAL은 OAuth 2.0와 함께 작동 하 여 MFA (다단계 인증)와 같은 추가 인증 및 권한 부여 시나리오 및 더 많은 유형의 SAML 인증을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="a4040-109">클라이언트로 작동 하는 다양 한 앱이 최신 인증을 활용 하 여 보안 리소스를 얻는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="a4040-110">비즈니스용 Skype 서버에서이 기술은 사용자에 게 리소스에 대 한 적절 한 권한 부여 수준을 제공 하기 위해 온-프레미스 클라이언트와 온-프레미스 서버 간에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="a4040-111">최신 인증 대화 (ADAL 및 OAuth 2.0을 기반으로 하는)는 몇 가지 일반적인 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="a4040-112">리소스에 대 한 요청을 수행 하는 클라이언트가 있는 경우이 경우 클라이언트는 비즈니스용 Skype입니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="a4040-113">클라이언트에 특정 수준의 액세스 권한이 필요 하 고이 리소스가 디렉터리 서비스에 의해 보호 되는 리소스 (이 경우 비즈니스용 Skype 서버)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="a4040-114">OAuth 연결, 즉 사용자에 게 리소스 액세스 권한을 *부여* 하는 전용 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="a4040-115">OAuth는 보다 설명적인 이름, ' 서버 간 ' 인증을 통해서도 가능 하며, 대개 S2S로 약어 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="a4040-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="a4040-116">ADAL (Business Server 현대 인증) 대화에서 비즈니스용 Skype 서버는 ADFS를 통해 통신 합니다 (Windows Server 2012 R2의 ADFS 3.0).</span><span class="sxs-lookup"><span data-stu-id="a4040-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="a4040-117">다른 Id 공급자 (IdP)를 사용 하 여 인증을 수행할 수 있지만 비즈니스용 Skype 서버를 ADFS와 직접 통신 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="a4040-118">비즈니스용 Skype 서버와 함께 작동 하도록 ADFS를 구성 하지 않은 경우 [adfs 설치](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4040-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="a4040-119">ADAL은 비즈니스용 Skype 서버 2015에 대 한 3 월 2016 누적 업데이트에 포함 되어 있으며 성공적인 구성에 필요한 비즈니스용 Skype에 대 한 3 월 2016 누적 업데이트를 설치 **해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="a4040-120">비즈니스용 Skype 서버 2019의 경우 제품의 초기 릴리스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4040-121">초기 릴리스 중에는 혼합 된 Skype 토폴로지가 포함 되어 있지 않은 경우에만 온-프레미스 환경의 최신 인증을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="a4040-122">예를 들어 환경이 비즈니스용 Skype 서버인 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="a4040-123">이 문은 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="a4040-124">ADAL에서 사용 되는 명령이 포함 된 ps1 파일을 포함 하는 PowerShell 패키지는 성공적인 구성을 위해 다운로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4040-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="a4040-125">비즈니스용 Skype에서 최신 인증을 구현 하는 방법에 대 한 자세한 내용은 [비즈니스용 skype에서 ADAL (최신 인증)을 사용 하는 방법](../../manage/authentication/use-adal.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4040-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
