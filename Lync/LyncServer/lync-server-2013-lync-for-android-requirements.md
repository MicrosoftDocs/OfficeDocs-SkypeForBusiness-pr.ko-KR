---
title: 'Lync Server 2013: Android 용 Lync 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cca08828dd91a7b6c26e11330f0e8839f4677be4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506055"
---
# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="bd57b-102">Lync Server 2013의 lync for Android 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd57b-102">Lync for Android requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd57b-103">_**마지막으로 수정 된 항목:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="bd57b-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="bd57b-104">Microsoft Lync 2013 Android 용 Microsoft Lync 2013는 Android 장치에서 연결 하는 조직의 사용자에 게 IM (인스턴트 메시징), 향상 된 현재 상태 및 Lync 모임 참가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="bd57b-105">이 항목에서는 선행 조건, 기술 요구 사항 및 필수 구성 요소를 비롯 하 여 Android 용 Lync 2013에 대 한 고려 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="bd57b-106">Lync for Android 선행 조건</span><span class="sxs-lookup"><span data-stu-id="bd57b-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="bd57b-107">Android 용 Lync 2013를 지원 하려면 Android 장치가 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="bd57b-108">Android 장치는 Tegra2 칩을 제외 하 고는 태블릿을 비롯 하 여 Android 4.0 이상 전화 또는 태블릿 지향 운영 체제를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="bd57b-109">장치에 1.2 GHz 듀얼 코어 이상의 CPU가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="bd57b-110">장치 카메라 (전면/후면) 해상도는 VGA 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="bd57b-111">다른 하드웨어 요구 사항은 Android 4.0 호환성 정의 문서와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="bd57b-112">기타 기술 고려 사항</span><span class="sxs-lookup"><span data-stu-id="bd57b-112">Other Technical Considerations</span></span>

<span data-ttu-id="bd57b-113">Android 장치 플랫폼에서 Lync 응용 프로그램은 백그라운드에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="bd57b-114">따라서 다른 모바일 장치 플랫폼과 달리 푸시 알림은 Android 장치에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="bd57b-115">Android 장치에서 Lync 응용 프로그램을 종료 하는 유일한 방법은 Lync에서 명시적으로 로그 아웃 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="bd57b-116">이 버전의 Lync 응용 프로그램은 Tegra 2 칩셋이 있는 장치에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57b-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

