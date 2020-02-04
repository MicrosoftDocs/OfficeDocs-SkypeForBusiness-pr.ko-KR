---
title: 'Lync Server 2013: 범주별 Lync Server cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d5d0dfc2540f5c623bff18f9739968983288e9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="bf699-102">범주별 Lync Server 2013 cmdlet</span><span class="sxs-lookup"><span data-stu-id="bf699-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf699-103">_**마지막으로 수정한 주제:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="bf699-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="bf699-104">Microsoft Lync Server 2013는 관리자가 명령줄에서 Lync Server를 관리할 수 있도록 특별히 디자인 된 거의 모든 550 cmdlet을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="bf699-105">Lync Server 관리 셸에서 cmdlet에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="bf699-106">다음과 같은 명령을 입력 하 여 명령줄에서 직접 cmdlet에 대 한 도움말을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="bf699-107">앞의 명령은 **CsVoicePolicy** cmdlet에 대해 사용할 수 있는 도움말을 모두 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="bf699-108">도움말을 검색 하려는 cmdlet의 이름으로 **CsVoicePolicy** 에 대 한 참조를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="bf699-109">Microsoft Lync Server 2013을 관리 하는 데 사용할 수 있는 전체 cmdlet 목록을 검색 하려면 Lync Server Management Shell 명령 프롬프트에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="bf699-110">필요한 cmdlet을 잘 모를 경우에는 분류 된 cmdlet 및 도움말 항목도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-110">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="bf699-111">일부 cmdlet은 두 개 이상의 범주에 표시 되며,이는 제품의 여러 영역에 적용 될 때 의도적인 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-111">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="bf699-112">범주 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-112">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bf699-113">비즈니스용 Skype cmdlet 참조가 docs.microsoft.com으로 이동 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="bf699-114">아래 링크를 클릭 하면 새 docs.microsoft.com 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="bf699-115">이제 콘텐츠가 열리고, GitHub를 통해 커뮤니티에서 기고 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf699-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="bf699-116">참여 하는 데 관심이 있으십니까?</span><span class="sxs-lookup"><span data-stu-id="bf699-116">Interested in contributing?</span></span> <span data-ttu-id="bf699-117">여기에 있는 리포지토리의 추가 정보를 확인 하세요.<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="bf699-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf699-118">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bf699-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf699-119"><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013의 사용자 관리 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-120"><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013의 음성 응용 프로그램 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf699-121"><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013의 클라이언트 관리 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013의 고급 엔터프라이즈 음성 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf699-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013의 메신저 대화 및 현재 상태 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013의 PSTN 연결 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf699-125"><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013의 회의 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013의 전화 및 장치 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf699-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013의 인프라 및 배포 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013의 마이그레이션 및 공존 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf699-129"><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013의 보안 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server 2013의 lync Server 관리 셸 구성 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf699-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013의 서버 역할 및 서비스 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-132"><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013의 모바일 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf699-133"><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013의 응용 프로그램 관리 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013의 영구 채팅 서버 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf699-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013의 페더레이션 및 외부 액세스 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bf699-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013의 중앙 집중화 된 로깅 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf699-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013의 엔터프라이즈 음성 cmdlet</a></span><span class="sxs-lookup"><span data-stu-id="bf699-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf699-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf699-138">See Also</span></span>


[<span data-ttu-id="bf699-139">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="bf699-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

