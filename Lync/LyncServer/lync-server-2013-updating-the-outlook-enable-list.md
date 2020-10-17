---
title: 'Lync Server 2013: Outlook 사용 목록 업데이트'
description: 'Lync Server 2013: Outlook 사용 목록을 업데이트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96edc327fa1b63d5da95eb6ea36a2296659910d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546234"
---
# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="7bf7d-103">Lync Server 2013에서 Outlook 사용 목록 업데이트</span><span class="sxs-lookup"><span data-stu-id="7bf7d-103">Updating the Outlook enable list in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7bf7d-104">_**마지막으로 수정 된 항목:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="7bf7d-104">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="7bf7d-105">Outlook 용 추가 기능 관리 목록에 Microsoft Lync 2013에 대 한 온라인 모임 추가 기능이 항상 사용 하도록 설정 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf7d-105">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="7bf7d-106">추가 기능 관리 목록 정책은 그룹 정책 관리 콘솔에 대한 Office 관리 템플릿 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bf7d-106">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="7bf7d-107">HKCU \\ 소프트웨어 정책 아래에 \\ \\ Microsoft \\ Office \\ 15.0 \\ Outlook15 \\ 복구 \\ AddinList의 레지스트리 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bf7d-107">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="7bf7d-108">ucaddin.dll의 값을이 키에 추가 하 고, 항상 사용 하도록 설정 하 고 사용자가 수동으로 사용 하지 않도록 설정할 수 없도록 ucaddin.dll 값을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bf7d-108">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="7bf7d-109">Outlook 추가 기능 목록에 ucaddin.dll 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="7bf7d-109">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="7bf7d-110">HKCU 소프트웨어 정책 아래에 있는 AddinList 레지스트리 키 \\ ( \\ \\ Microsoft \\ Office \\ 15.0 \\ Outlook15 복원성 AddinList에 \\ \\ 있음)에 다음 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bf7d-110">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="7bf7d-111">레지스트리 유형 = REG \_ SZ</span><span class="sxs-lookup"><span data-stu-id="7bf7d-111">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="7bf7d-112">이름 = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="7bf7d-112">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="7bf7d-113">값 = 1(추가 기능이 항상 설정되고 최종 사용자가 관리할 수 없도록 지정)</span><span class="sxs-lookup"><span data-stu-id="7bf7d-113">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

