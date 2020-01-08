---
title: 'Lync Server 2013: lync에 대 한 Skype 연결 켜기에 대 한 참고 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a3c3327a731f3a7c6bba25469376ffffeee8d8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="b5df9-102">Lync Online 고객을 위한 lync Server 2013의 Lync-Skype 연결에 대 한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="b5df9-102">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5df9-103">_**마지막으로 수정한 주제:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="b5df9-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="b5df9-104">이 문서는 Lync Server 온-프레미스 관리자가 Lync-Skype 연결을 설정 하는 데 도움이 되도록 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-104">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="b5df9-105">Lync-Skype 연결은 Office 365의 일부인 Lync Online의 기능 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-105">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365.</span></span> <span data-ttu-id="b5df9-106">Office 365 포털 내 Lync 관리 센터에서 Lync-Skype 연결 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-106">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the Office 365 portal.</span></span>

<span data-ttu-id="b5df9-107">Office 365 중간 규모 비즈니스, Office 365 Enterprise, Office 365 교육 및 정부용 Office 365: Office 365 포털에 로그인 하 여 **Lync 관리 센터로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-107">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="b5df9-108">**외부 통신**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-108">Go to **External Communications**.</span></span> <span data-ttu-id="b5df9-109">**공용 IM 서비스 공급자**에서 **사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-109">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="b5df9-110">Lync-Skype 연결에 대 한 개별 사용자 액세스를 제어 하려는 경우 개별 사용자의 외부 통신 설정을 편집 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-110">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="b5df9-111">Office 365 Small Business Premium의 경우 Office 365에 로그인 하 고 **관리자 \> 서비스 설정 \> 메신저 인스턴트 메시지, 모임 및 회의**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-111">For Office 365 Small Business Premium: Sign in to Office 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="b5df9-112">외부 통신을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-112">Turn on External communications.</span></span> <span data-ttu-id="b5df9-113">외부 통신 스위치는 lync를 사용 하는 다른 조직과의 통신 및 Skype 연결을 모두 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-113">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="b5df9-114">Lync Online 사용을 시작한 시점에 따라 "켜 짐" 상태의 외부 통신 스위치는 처음에 다른 Lync 조직과의 통신이 활성화 되어 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-114">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="b5df9-115">Lync-Skype 연결을 설정 하려면, 스위치를 껐다가 다시 켜 놓기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5df9-115">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

