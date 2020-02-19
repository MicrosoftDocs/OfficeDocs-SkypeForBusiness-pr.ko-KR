---
title: 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27a2298dffdcb868646f2d4d4513702a4c4554d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="30539-102">Lync Server 2013에서 전화 접속 회의 PIN (개인 식별 번호) 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="30539-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30539-103">_**마지막으로 수정 된 항목:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="30539-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="30539-104">Lync Server 2013 조직의 AD DS (Active Directory 도메인 서비스) 자격 증명이 있는 사용자는 PIN (개인 식별 번호)을 사용 하 여 인증 된 사용자로 전화 접속 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30539-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="30539-105">PIN 정책은 전화 접속 회의 Pin이 작동 하는 방식에 대 한 규칙을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="30539-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="30539-106">특정 정책을 사이트 또는 특정 사용자 그룹에 적용 하려는 경우 새 PIN 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30539-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="30539-107">전체 조직에 동일한 PIN 정책을 사용 하려는 경우에는 전역 PIN 정책을 사용 하 여 필요에 따라 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30539-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="30539-108">PIN 정책은 가장 좁은 범위의 사용자에 게 광범위 한 범위에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30539-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="30539-109">사용자에 게 사용자 수준 PIN 정책을 할당 하면 해당 설정이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30539-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="30539-110">사용자 정책을 할당 하지 않으면 사이트 수준 PIN 정책이 적용 됩니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="30539-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="30539-111">사용자 또는 사이트 정책이 적용 되지 않는 경우에는 전역 PIN 정책이 기본 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30539-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="30539-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="30539-112">In This Section</span></span>

  - [<span data-ttu-id="30539-113">Lync Server 2013에서 기본 전화 접속 회의 PIN 설정 수정</span><span class="sxs-lookup"><span data-stu-id="30539-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="30539-114">Lync Server 2013에서 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="30539-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="30539-115">Lync Server 2013의 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="30539-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

