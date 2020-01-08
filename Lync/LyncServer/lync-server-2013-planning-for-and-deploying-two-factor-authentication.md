---
title: Lync Server 2013:2 단계 인증 계획 및 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c902a3abd0035cbffa5bb10ed05cad6fa7bcc6b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="ed2d1-102">Lync Server 2013의 2 단계 인증</span><span class="sxs-lookup"><span data-stu-id="ed2d1-102">Two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed2d1-103">_**마지막으로 수정한 주제:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="ed2d1-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="ed2d1-104">2 단계 인증은 사용자가 두 가지 인증 조건 즉, 사용자 이름/암호 조합 및 토큰 또는 인증서를 만족 하도록 요구 하 여 향상 된 보안을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2d1-104">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="ed2d1-105">이것을 "보유 하 고 있는 물건" 이라고 하는 것이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2d1-105">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="ed2d1-106">인증서를 사용 하는 2 단계 인증의 일반적인 예는 스마트 카드를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ed2d1-106">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="ed2d1-107">스마트 카드에는 사용자 계정과 연결 된 인증서가 포함 되며, 서버에 저장 된 사용자 및 인증서 정보에 대해 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed2d1-107">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="ed2d1-108">제공 된 인증서와 사용자 정보 (사용자 이름 및 암호)를 비교 하 여 서버는 자격 증명의 유효성을 검사 하 고 사용자를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2d1-108">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed2d1-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ed2d1-109">In This Section</span></span>

[<span data-ttu-id="ed2d1-110">Lync Server 2013의 2 단계 인증 계획</span><span class="sxs-lookup"><span data-stu-id="ed2d1-110">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="ed2d1-111">Lync Server 2013에서 2 단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="ed2d1-111">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="ed2d1-112">Lync 클라이언트 및 Lync Server 2013에서 2 단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="ed2d1-112">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

