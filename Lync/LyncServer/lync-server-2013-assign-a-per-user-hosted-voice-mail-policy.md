---
title: 'Lync Server 2013: 사용자 단위 호스팅 음성 메일 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978929"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="51d49-102">Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="51d49-102">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>

 


<span data-ttu-id="51d49-103">하나 이상의 사용자 단위 호스팅 음성 메일 정책을 배포 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-103">Deploying one or more per-user hosted voice mail policies is optional.</span></span> <span data-ttu-id="51d49-104">사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-104">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span>

<span data-ttu-id="51d49-105">사용자 단위 호스팅 음성 메일 정책의 할당을 할당 하거나 제거 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51d49-105">For details about assigning or removing the assignment of per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="51d49-106">부여-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="51d49-106">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="51d49-107">제거-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="51d49-107">Remove-CsHostedVoicemailPolicy</span></span>

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="51d49-108">사용자 단위 호스팅 음성 메일 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="51d49-108">To assign a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="51d49-109">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="51d49-110">CsHostedVoicemailPolicy cmdlet을 실행 하 여 개별 사용자, 그룹 및 연락처 개체에 사용자 단위 호스팅 음성 메일 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-110">Run the Grant-CsHostedVoicemailPolicy cmdlet to assign the per-user hosted voice mail policy to individual users, groups, and contact objects.</span></span> <span data-ttu-id="51d49-111">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-111">For example, run:</span></span>
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    <span data-ttu-id="51d49-112">이 예제에서는 ExRedmond 호스팅 음성 메일 정책을 사용자: 진구 Myer에 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-112">This example assigned the ExRedmond hosted voice mail policy to user Ken Myer.</span></span>
    
    <span data-ttu-id="51d49-113">**Id** 수정할 사용자 계정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-113">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="51d49-114">Id 값은 다음 형식 중 하나를 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-114">The Identity value can be specified using any of the following formats:</span></span>
    
      - <span data-ttu-id="51d49-115">사용자의 SIP 주소</span><span class="sxs-lookup"><span data-stu-id="51d49-115">The user's SIP address</span></span>
    
      - <span data-ttu-id="51d49-116">사용자의 Active Directory 사용자-주 이름</span><span class="sxs-lookup"><span data-stu-id="51d49-116">The user's Active Directory User-Principal-Name</span></span>
    
      - <span data-ttu-id="51d49-117">사용자의 도메인\\로그온 이름 (예: contoso\\kenmyer)</span><span class="sxs-lookup"><span data-stu-id="51d49-117">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
    
      - <span data-ttu-id="51d49-118">사용자의 Active Directory 도메인 서비스 표시 이름 (예:: 진구 Myer)</span><span class="sxs-lookup"><span data-stu-id="51d49-118">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="51d49-119">표시 이름을 Id 값으로 사용 하는 경우 별표 (\*) 와일드 카드 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-119">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="51d49-120">예를 들어 Id "\* smith"는 "smith" 문자열 값으로 끝나는 표시 이름을 가진 모든 사용자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-120">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="51d49-121">SAM-계정 이름이 포리스트에서 고유 하지 않아도 되므로 사용자의 Active Directory SAM-계정 이름을 Id 값으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51d49-121">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>


