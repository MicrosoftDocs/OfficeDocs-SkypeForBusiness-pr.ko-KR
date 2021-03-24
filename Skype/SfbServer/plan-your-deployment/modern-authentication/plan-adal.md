---
title: 비즈니스용 Skype를 사용하는 ADAL(최신 인증) 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 이 문서에서는 ADAL(Active Directory 인증 라이브러리) 및 OAuth 2.0 기반의 최신 인증에 대해 설명합니다.
ms.openlocfilehash: 1df07491881b90efc16c97e7cd5cec0953cfb346
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096614"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="26236-103">비즈니스용 Skype에서 ADAL(최신 인증)을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="26236-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="26236-104">이 문서에서는 2016년 3월 비즈니스용 Skype for Business Server 2015 누적 업데이트 또는 비즈니스용 Skype 서버 2019의 초기 릴리스에서 찾을 수 있는 최신 인증(ADAL(Active Directory 인증 라이브러리) 및 OAuth 2.0 기반)을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="26236-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="26236-105">ADAL이란?</span><span class="sxs-lookup"><span data-stu-id="26236-105">What is ADAL?</span></span>

<span data-ttu-id="26236-106">ADAL은 'Active Directory 인증 라이브러리'의 약어로, OAuth 2.0과 함께 최신 인증의 기조입니다.</span><span class="sxs-lookup"><span data-stu-id="26236-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="26236-107">이 코드 라이브러리는 보안 토큰을 통해 클라이언트 응용 프로그램(예: 비즈니스용 Skype)에서 디렉터리의 보안 리소스를 사용할 수 있도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26236-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="26236-108">ADAL은 OAuth 2.0과 함께 작동하여 MFA(Multi-Factor Authentication) 및 더 많은 형태의 SAML 인증과 같은 더 많은 인증 및 권한 부여 시나리오를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="26236-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="26236-109">클라이언트 역할을 하는 다양한 앱은 보안 리소스에 대한 도움말을 위해 최신 인증을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26236-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="26236-110">비즈니스용 Skype 서버에서 이 기술은 사용자에게 리소스에 대한 적절한 수준의 권한 부여를 제공하기 위해 사내 클라이언트와 사내 서버 간에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26236-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="26236-111">ADAL 및 OAuth 2.0 기반의 최신 인증 대화에는 몇 가지 공통 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26236-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="26236-112">리소스 요청을 하는 클라이언트가 있습니다. 이 경우 클라이언트는 비즈니스용 Skype입니다.</span><span class="sxs-lookup"><span data-stu-id="26236-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="26236-113">클라이언트에 특정 수준의 액세스가 필요한 리소스가 있으며 이 리소스는 디렉터리 서비스에 의해 보호됩니다(이 경우 리소스는 비즈니스용 Skype 서버).</span><span class="sxs-lookup"><span data-stu-id="26236-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="26236-114">즉, 사용자가 리소스에 액세스할 수 있도록 권한을 부여하는  데 전용으로 사용할 수 있는 OAuth 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26236-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="26236-115">(OAuth는 보다 설명적인 이름인 '서버 간' auth로도 알려져 있으며 종종 S2S로 약식으로도 알려져 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="26236-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="26236-116">비즈니스용 Skype 서버 ADAL(최신 인증) 대화에서 비즈니스용 Skype 서버는 ADFS(WINDOWS SERVER 2012 R2의 ADFS 3.0)를 통해 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="26236-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="26236-117">인증은 다른 IdP(ID 공급자)를 사용하여 진행될 수 있지만, ADFS와 직접 통신하도록 비즈니스용 Skype 서버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26236-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="26236-118">비즈니스용 Skype 서버에서 작동하도록 ADFS를 구성하지 않은 경우 ADFS 설치를 [완료하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="26236-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>
  
<span data-ttu-id="26236-119">ADAL은 비즈니스용 Skype 서버 2015 2016년 3월 누적 업데이트에 포함되어 있으며, 성공적인 구성을  위해 비즈니스용 Skype에 대한 2016년 3월 누적 업데이트를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26236-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="26236-120">비즈니스용 Skype 서버 2019의 경우 제품의 초기 릴리스부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26236-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26236-121">초기 릴리스 동안에는 혼합 Skype 토폴로지가 없는 경우만 사내 환경의 최신 인증이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="26236-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="26236-122">예를 들어 환경이 전적으로 비즈니스용 Skype 서버인 경우</span><span class="sxs-lookup"><span data-stu-id="26236-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="26236-123">이 설명은 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26236-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="26236-124">성공적인 구성을 위해 ADAL에서 사용하는 명령이 있는 .ps1 파일을 포함한 PowerShell 패키지를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26236-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="26236-125">비즈니스용 Skype에서 최신 인증을 구현하는 방법에 대한 자세한 내용은 비즈니스용 [Skype에서 ADAL(최신 인증)을 사용하는 방법을 참조하세요.](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span><span class="sxs-lookup"><span data-stu-id="26236-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span></span>