---
title: 'Lync Server 2013: Outlook 사용 목록 업데이트'
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
ms.openlocfilehash: 376c5788d535cd893b2261dcddcb1fe05d676005
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a><span data-ttu-id="0825f-102">Lync Server 2013에서 Outlook 사용 목록 업데이트</span><span class="sxs-lookup"><span data-stu-id="0825f-102">Updating the Outlook enable list in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0825f-103">_**마지막으로 수정 된 항목:** 2013-01-07_</span><span class="sxs-lookup"><span data-stu-id="0825f-103">_**Topic Last Modified:** 2013-01-07_</span></span>

<span data-ttu-id="0825f-104">Outlook 용 추가 기능 관리 목록에 Microsoft Lync 2013에 대 한 온라인 모임 추가 기능이 항상 사용 하도록 설정 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0825f-104">You can ensure that Online Meeting Add-in for Microsoft Lync 2013 always remains enabled for users by creating a policy that includes it in the Add-in Management List for Outlook.</span></span> <span data-ttu-id="0825f-105">추가 기능 관리 목록 정책은 그룹 정책 관리 콘솔에 대한 Office 관리 템플릿 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0825f-105">The Add-in Management List policy is included in the Office administrative template files for the Group Policy Management Console.</span></span> <span data-ttu-id="0825f-106">\\HKCU\\소프트웨어 정책\\아래에 Microsoft\\Office\\15.0\\Outlook15\\복구\\AddinList의 레지스트리 키를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0825f-106">It creates a registry key under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList.</span></span> <span data-ttu-id="0825f-107">이 키에 c u c l i c e c i c e c i c e c i c c e c e c의 값을 추가 하 고이 값을 사용 하도록 설정 하 여 사용자가 수동으로 사용 하지 않도록 설정할 수 없도록</span><span class="sxs-lookup"><span data-stu-id="0825f-107">You can add a value for the ucaddin.dll to this key, and configure the ucaddin.dll value so that it is always enabled and so that users cannot manually disable it</span></span>

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a><span data-ttu-id="0825f-108">Outlook 추가 기능 목록에 기타 기능을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="0825f-108">To Add ucaddin.dll to the Outlook Add-in List</span></span>

  - <span data-ttu-id="0825f-109">\\HKCU\\소프트웨어 정책\\아래에 있는 AddinList 레지스트리 키 (Microsoft\\Office\\15.0\\Outlook15\\복원성\\AddinList에 있음)에 다음 값을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0825f-109">To the AddinList registry key, located under HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\Resiliency\\AddinList, add the following value:</span></span>
    
      - <span data-ttu-id="0825f-110">레지스트리 유형 = REG\_SZ</span><span class="sxs-lookup"><span data-stu-id="0825f-110">Registry Type = REG\_SZ</span></span>
    
      - <span data-ttu-id="0825f-111">이름 = ucaddin.dll</span><span class="sxs-lookup"><span data-stu-id="0825f-111">Name = ucaddin.dll</span></span>
    
      - <span data-ttu-id="0825f-112">값 = 1(추가 기능이 항상 설정되고 최종 사용자가 관리할 수 없도록 지정)</span><span class="sxs-lookup"><span data-stu-id="0825f-112">Value = 1 (specifies that the add-in is always enabled and cannot be managed by the end user)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

