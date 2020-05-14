---
title: 비즈니스용 Skype의 최신 인증 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 다른 제품과의 통합을 포함 하 여 비즈니스용 Skype 서버에 대 한 인증 및 권한 부여에 대 한 계획 항목
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221582"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="892c3-103">비즈니스용 Skype의 인증 및 권한 부여 논의</span><span class="sxs-lookup"><span data-stu-id="892c3-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="892c3-104">인증 및 권한 부여는 관련 된 개념 이지만 다른 작업을 수행 하는 것이 좋습니다 (두 가지 모두 필요 함).</span><span class="sxs-lookup"><span data-stu-id="892c3-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="892c3-105">Authenciation (인증)은 비밀에만 적합 하며, 유효한 사용자가 알고 있거나 갖고 있으며 암호, 코드, 지문, 인증서, 사용자에 대 한 클레임 조합 또는 함께 사용 되는 이러한 항목의 조합이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="892c3-106">인증는 사용자의 신원을 입증 하기 위한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="892c3-107">권한 부여 (인증)는 사용자가 누구 인지 입증 한 후에 액세스 하는 것과 관련 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="892c3-108">이 개체는 보기, 편집 및 기타 액세스를 허용한 사용자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="892c3-109">예를 들어 SharePoint Online에 대 한 강력한 사이트 모음 관리자 액세스 권한이 있지만 비즈니스용 Skype Online과 같은 다른 온라인 작업 환경으로 전환 하는 경우에는 서버 구성을 변경 하지 않고 사용자 문제를 해결 하는 데 필요한 권한이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="892c3-110">Exchange Online과 같은 세 번째 작업 부하에서는 평균 사용자 액세스만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="892c3-111">인증에서는 서비스/진행에 대 한 액세스 권한, 응용 프로그램, 파일 및 기타 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="892c3-112">이 예에는 SharePoint 및 Exchange online과 같은 온라인 속성이 포함 되어 있지만 인증 및 인증의 프로세스는 온-프레미스와 하이브리드 프레미스에서 동일한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="892c3-113">궁극적으로, AAD Connect 및 ADFS와 같은 도구는 온-프레미스 계정 및 암호를 클라우드 AD (Azure AD)로 동기화 하거나, 사용자에 게 자격 증명을 입력 하 라는 메시지가 자주 표시 되지 않도록 하 여 인증 및 인증 스토리에 참여 하 게 함으로써 클라우드의 워크 로드를 전환 하 여 Single Sign-on 시나리오를 만드는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="892c3-114">하지만 이러한 사용자는 인증 또는 인증을 책임 지는 메커니즘의 일부일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="892c3-115">오늘날 대부분의 기술은 이러한 프로세스 (인증 및 인증)를 하나의 메커니즘으로 간주 하며, 인증 프로세스에 대 한 많은 참조를 통해 해당 권한 부여도 함께 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="892c3-116">사용자 액세스의 첫 번째 단계는 인증이 고 사용자가 말하고 있다는 것을 입증 하 고, 인증에 사용 되는 사람을 결정 하는 데 도움이 됩니다 (공개 권한 부여 또는 OAuth 표시).</span><span class="sxs-lookup"><span data-stu-id="892c3-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="892c3-117">인증 및 권한 부여 계획 항목</span><span class="sxs-lookup"><span data-stu-id="892c3-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="892c3-118">비즈니스용 Skype에서 ADAL (최신 인증)을 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="892c3-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="892c3-119">최신 인증과 함께 지원 되는 비즈니스용 Skype 토폴로지</span><span class="sxs-lookup"><span data-stu-id="892c3-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="892c3-120">네트워크에서 내부적으로 또는 외부적으로 레거시 인증 방법을 해제할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="892c3-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

