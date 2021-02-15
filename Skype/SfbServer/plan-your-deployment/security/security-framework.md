---
title: 비즈니스용 Skype 서버용 보안 프레임워크
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 이 섹션에서는 비즈니스용 Skype 서버의 보안 프레임워크를 구성하는 기본 요소에 대한 개요를 제공합니다. 이러한 요소가 함께 작동되는 방식에 대한 이해는 특정 비즈니스용 Skype 서버 배포의 보안과 관련한 합리적 결정을 내리는 데 필수적입니다.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832098"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="fe037-104">비즈니스용 Skype 서버용 보안 프레임워크</span><span class="sxs-lookup"><span data-stu-id="fe037-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="fe037-105">이 섹션에서는 비즈니스용 Skype 서버의 보안 프레임워크를 구성하는 기본 요소에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="fe037-106">이러한 요소가 함께 작동되는 방식에 대한 이해는 특정 비즈니스용 Skype 서버 배포의 보안과 관련한 합리적 결정을 내리는 데 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="fe037-107">이러한 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="fe037-108">AD DS(Active Directory 도메인 서비스)는 사용자 계정 및 네트워크 리소스에 대한 단일 트러스트된 백 엔드 리포지토리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="fe037-109">Role-Based(RBAC)를 사용하면 높은 보안 표준을 유지하면서 관리 작업을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="fe037-110">PKI(공개 키 인프라)는 신뢰할 수 있는 CAS(인증 기관)에서 발급한 인증서를 사용하여 서버를 인증하고 데이터 무결성을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="fe037-111">TLS(전송 계층 보안), HTTPS over SSL(HTTPS) 및 MTLS(상호 TLS)를 사용하면 끝점 인증 및 IM 암호화를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-111">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="fe037-112">지점 대 지점 오디오, 비디오 및 응용 프로그램 공유 스트림은 SRTP(Secure Real-Time Transport Protocol)를 사용하여 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-112">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="fe037-113">가능한 경우 사용자 인증을 위한 업계 표준 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="fe037-114">Windows PowerShell 사용자가 스크립트를 쉽게 또는 무의미하게 실행할 수 없는 보안 기능을 기본적으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="fe037-115">이러한 기본 보안 요소는 함께 작동하여 신뢰할 수 있는 사용자, 서버, 연결 및 작업을 정의하여 비즈니스용 Skype 서버의 보안 기반을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="fe037-116">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fe037-116">In this section</span></span>

<span data-ttu-id="fe037-117">이 섹션의 항목에서는 이러한 각 기본 요소가 비즈니스용 Skype 서버 인프라의 보안을 향상시키는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fe037-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="fe037-118">비즈니스용 Skype 서버용 Active Directory 도메인 서비스</span><span class="sxs-lookup"><span data-stu-id="fe037-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="fe037-119">비즈니스용 Skype 서버용 RBAC(역할 기반 액세스 제어)</span><span class="sxs-lookup"><span data-stu-id="fe037-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="fe037-120">비즈니스용 Skype 서버의 공개 키 인프라</span><span class="sxs-lookup"><span data-stu-id="fe037-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="fe037-121">비즈니스용 Skype 서버의 TLS 및 MTLS</span><span class="sxs-lookup"><span data-stu-id="fe037-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="fe037-122">비즈니스용 Skype 서버 암호화</span><span class="sxs-lookup"><span data-stu-id="fe037-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="fe037-123">비즈니스용 Skype 서버에 대한 사용자 및 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="fe037-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="fe037-124">Windows PowerShell 및 비즈니스용 Skype 서버 관리 도구</span><span class="sxs-lookup"><span data-stu-id="fe037-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

