---
title: 비즈니스용 Skype 서버용 보안 프레임 워크
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 이 섹션에서는 비즈니스용 Skype 서버에 대 한 보안 프레임 워크를 구성 하는 기본 요소에 대해 간략하게 설명 합니다. 이러한 요소가 함께 작동 하는 방식을 이해 하는 것은 특정 비즈니스용 Skype 서버 배포 보안에 대 한 의사 결정을 내리는 데 반드시 필요 합니다.
ms.openlocfilehash: 8b82b09a8220139abe62ac4503ad8a7eddc28e99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196829"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="dfbbb-104">비즈니스용 Skype 서버용 보안 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="dfbbb-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="dfbbb-105">이 섹션에서는 비즈니스용 Skype 서버에 대 한 보안 프레임 워크를 구성 하는 기본 요소에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="dfbbb-106">이러한 요소가 함께 작동 하는 방식을 이해 하는 것은 특정 비즈니스용 Skype 서버 배포 보안에 대 한 의사 결정을 내리는 데 반드시 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="dfbbb-107">이러한 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="dfbbb-108">AD DS (Active Directory 도메인 서비스)는 사용자 계정 및 네트워크 리소스에 대해 신뢰할 수 있는 단일 백 엔드 리포지토리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="dfbbb-109">RBAC (역할 기반 액세스 제어)를 사용 하 여 보안을 위해 높은 표준을 유지 하면서 관리 작업을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="dfbbb-110">PKI (공개 키 인프라)는 신뢰할 수 있는 Ca (인증 기관)에서 발급 한 인증서를 사용 하 여 서버를 인증 하 고 데이터 무결성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="dfbbb-111">TLS (전송 계층 보안), https over SSL (HTTPS) 및 상호 TLS (MTLS)로 끝점 인증 및 IM 암호화를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-111">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="dfbbb-112">지점간 오디오, 비디오 및 응용 프로그램 공유 스트림은 보안 실시간 전송 프로토콜 (SRTP)을 사용 하 여 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-112">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="dfbbb-113">가능 하면 사용자 인증을 위한 업계 표준 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="dfbbb-114">Windows PowerShell은 사용자가 스크립트를 쉽게 실행할 수 없도록 기본적으로 활성화 된 보안 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="dfbbb-115">이러한 기본 보안 요소는 신뢰할 수 있는 사용자, 서버, 연결, 작업을 정의 하 여 비즈니스용 Skype 서버를 위한 안전한 토대를 보장 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dfbbb-116">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="dfbbb-116">In this section</span></span>

<span data-ttu-id="dfbbb-117">이 섹션의 항목에서는 이러한 기본 요소가 각각의 비즈니스용 Skype 서버 인프라의 보안을 강화 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfbbb-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="dfbbb-118">비즈니스용 Skype 서버용 Active Directory 도메인 서비스</span><span class="sxs-lookup"><span data-stu-id="dfbbb-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="dfbbb-119">비즈니스용 Skype 서버용에 대 한 RBAC (역할 기반 액세스 제어)</span><span class="sxs-lookup"><span data-stu-id="dfbbb-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="dfbbb-120">비즈니스용 Skype 서버용 공개 키 인프라</span><span class="sxs-lookup"><span data-stu-id="dfbbb-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="dfbbb-121">비즈니스용 Skype 서버용 TLS 및 MTLS</span><span class="sxs-lookup"><span data-stu-id="dfbbb-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="dfbbb-122">비즈니스용 Skype 서버 암호화</span><span class="sxs-lookup"><span data-stu-id="dfbbb-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="dfbbb-123">비즈니스용 Skype 서버에 대 한 사용자 및 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="dfbbb-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="dfbbb-124">Windows PowerShell 및 비즈니스용 Skype 서버 관리 도구</span><span class="sxs-lookup"><span data-stu-id="dfbbb-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

