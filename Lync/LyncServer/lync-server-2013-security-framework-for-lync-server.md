---
title: 'Lync Server 2013: Lync Server의 보안 프레임 워크'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="cc073-102">Lync Server 2013의 보안 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="cc073-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc073-103">_**마지막으로 수정한 주제:** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="cc073-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="cc073-104">이 섹션에서는 Microsoft Lync Server 2013의 보안 프레임 워크를 구성 하는 기본 요소에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="cc073-105">이러한 요소가 함께 작동 하는 방식을 이해 하는 것은 특정 Lync Server 2013 배포 보안에 대 한 의사 결정을 내리는 데 반드시 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="cc073-106">이러한 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-106">These elements are as follows:</span></span>

  - <span data-ttu-id="cc073-107">AD DS (Active Directory 도메인 서비스)는 사용자 계정 및 네트워크 리소스에 대해 신뢰할 수 있는 단일 백 엔드 리포지토리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="cc073-108">RBAC (역할 기반 액세스 제어)를 사용 하 여 보안을 위해 높은 표준을 유지 하면서 관리 작업을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="cc073-109">PKI (공개 키 인프라)는 신뢰할 수 있는 Ca (인증 기관)에서 발급 한 인증서를 사용 하 여 서버를 인증 하 고 데이터 무결성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="cc073-110">TLS (전송 계층 보안), https over SSL (HTTPS) 및 상호 TLS (MTLS)로 끝점 인증 및 IM 암호화를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-110">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="cc073-111">지점간 오디오, 비디오 및 응용 프로그램 공유 스트림은 보안 실시간 전송 프로토콜 (SRTP)을 사용 하 여 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-111">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="cc073-112">가능 하면 사용자 인증을 위한 업계 표준 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="cc073-113">Windows PowerShell은 사용자가 스크립트를 쉽게 실행할 수 없도록 기본적으로 활성화 된 보안 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="cc073-114">이러한 기본 보안 요소는 Lync Server 2013의 보안 기반을 보장 하는 데 도움이 되는 신뢰할 수 있는 사용자, 서버, 연결, 작업을 정의 하기 위해 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc073-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="cc073-115">In This Section</span></span>

<span data-ttu-id="cc073-116">이 섹션의 항목에서는 이러한 기본 요소의 작동 방식으로 Lync Server 인프라의 보안을 강화 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc073-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="cc073-117">Lync Server 2013의 Active Directory 도메인 서비스</span><span class="sxs-lookup"><span data-stu-id="cc073-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="cc073-118">Lync Server 2013에 대 한 RBAC (역할 기반 액세스 제어)</span><span class="sxs-lookup"><span data-stu-id="cc073-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="cc073-119">Lync Server 2013의 공개 키 인프라</span><span class="sxs-lookup"><span data-stu-id="cc073-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="cc073-120">Lync Server 2013 용 TLS 및 MTLS</span><span class="sxs-lookup"><span data-stu-id="cc073-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="cc073-121">Lync Server 2013 암호화</span><span class="sxs-lookup"><span data-stu-id="cc073-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="cc073-122">Lync Server 2013에 대 한 사용자 및 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="cc073-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="cc073-123">Windows PowerShell 및 Lync Server 2013 관리 도구</span><span class="sxs-lookup"><span data-stu-id="cc073-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

