---
title: Lync Server 2013:2 단계 인증 계획 및 배포
description: Lync Server 2013:2 단계 인증을 계획 하 고 배포 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1e04fa7a0c1184152328882a7c7b4bea8e42ec0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579504"
---
# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="eba2e-103">Lync Server 2013의 2 단계 인증</span><span class="sxs-lookup"><span data-stu-id="eba2e-103">Two-factor authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eba2e-104">_**마지막으로 수정 된 항목:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="eba2e-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="eba2e-105">이중 인증을 사용 하면 사용자가 인증 기준 두 가지 인 user name/password 조합과 토큰 또는 인증서를 사용 하도록 요구 하 여 보안이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eba2e-105">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="eba2e-106">이를 "사용자가가지고 있는 항목, 알고 있는 항목"이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba2e-106">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="eba2e-107">인증서에 대 한 2 단계 인증의 일반적인 예로 스마트 카드 사용을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba2e-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="eba2e-108">스마트 카드에는 사용자 계정과 연결 된 인증서가 포함 되어 있으며 서버에 저장 된 사용자 및 인증서 정보에 대해 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eba2e-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="eba2e-109">사용자 정보 (사용자 이름 및 암호)를 제공 된 인증서와 비교 하 여 서버에서 자격 증명의 유효성을 검사 하 고 사용자를 인증 합니다.</span><span class="sxs-lookup"><span data-stu-id="eba2e-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eba2e-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="eba2e-110">In This Section</span></span>

[<span data-ttu-id="eba2e-111">Lync Server 2013의 2 단계 인증 계획</span><span class="sxs-lookup"><span data-stu-id="eba2e-111">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="eba2e-112">Lync Server 2013에서 2 단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="eba2e-112">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="eba2e-113">Lync 클라이언트 및 Lync Server 2013에서 2 단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="eba2e-113">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

