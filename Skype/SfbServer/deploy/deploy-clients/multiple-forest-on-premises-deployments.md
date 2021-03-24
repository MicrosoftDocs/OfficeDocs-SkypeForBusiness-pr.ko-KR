---
title: Skype 룸 시스템 다중 포리스트 사내 배포
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 이 항목을 통해 다중 포리스트의 사내 환경에서 Skype 룸 시스템을 배포하는 방법을 배워야 합니다.
ms.openlocfilehash: d215ce13059c414d6c6142d7cd1e93ea9011c97b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093532"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="3d463-103">Skype 룸 시스템 다중 포리스트 사내 배포</span><span class="sxs-lookup"><span data-stu-id="3d463-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="3d463-104">이 항목을 통해 다중 포리스트의 사내 환경에서 Skype 룸 시스템을 배포하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d463-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d463-105">여러 포리스트에 배포하려면 Skype 룸 시스템에 2014년 8월 26일 Exchange Server 2013 CU6이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d463-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="3d463-106">Skype 룸 시스템에 대해 기존 사서함을 다시 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d463-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="3d463-107">Skype 룸 시스템에 대해 새(이전 사서함 삭제 및 다시 만들기) 리소스 사서함을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="3d463-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="3d463-108">사서함을 삭제하여 손실된 모임을 복원하려면 삭제된 사서함 연결 또는 [복원을 참조합니다.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="3d463-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="3d463-109">사서함을 만들고 나면 사서함을 Set-CalendarProcessing 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d463-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="3d463-110">자세한 내용은 Single forest on-premises deployments에서 3-6단계를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d463-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="3d463-111">Skype 룸 시스템에 대한 Exchange 리소스 사서함을 만들고 나면 비즈니스용 Skype의 단일 포리스트에 대한 비즈니스용 Skype 시스템 계정 사용의 단계에 따라 비즈니스용 Skype에 대해 계정을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d463-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="3d463-112">옵션 1: 새 리소스 사서함 만들기</span><span class="sxs-lookup"><span data-stu-id="3d463-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="3d463-113">다중 포리스트 환경에서 Skype 룸 시스템을 배포하는 경우:</span><span class="sxs-lookup"><span data-stu-id="3d463-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="3d463-114">Active Directory(인증 포리스트)에서 연결된 사용자(LinkedRoomTest)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d463-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="3d463-115">관리 셸에서 다음 Exchange Server 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3d463-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="3d463-116">옵션 2: 기존 채팅방 사서함을 Skype 룸 시스템(연결된) 리소스 사서함으로 변경</span><span class="sxs-lookup"><span data-stu-id="3d463-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```