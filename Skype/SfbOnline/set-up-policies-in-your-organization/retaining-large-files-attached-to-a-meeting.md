---
title: 모임에 연결된 큰 비즈니스용 Skype 유지
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 참가자가 열고 다운로드할 수 있는 비즈니스용 Skype 모임에 파일을 첨부할 수 있습니다. 모임에 비즈니스용 Skype 첨부된 파일은 소송 보류에 사서함이 배치되거나, Microsoft 365 Office 365 보존 정책이 적용되거나, 규정 준수 센터의 eDiscovery 사례와 연결된 보류 Microsoft 365 있는 모든 참가자의 사서함에 보관됩니다. 이 콘텐츠는 참가자의 사서함에 복구 가능한 항목 폴더에 저장됩니다.
ms.openlocfilehash: 74605b9aebf6d83619282d9cfc9094216d2fe6f1
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240110"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="dc5f8-105">모임에 연결된 큰 비즈니스용 Skype 유지</span><span class="sxs-lookup"><span data-stu-id="dc5f8-105">Retaining large files attached to a Skype for Business meeting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="dc5f8-106">참가자가 열고 다운로드할 수 있는 비즈니스용 Skype 모임에 파일을 첨부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="dc5f8-107">모임에 비즈니스용 Skype 첨부된 파일은 소송 보류에 사서함이 배치되거나, Microsoft 365 Office 365 보존 정책이 적용되거나, 규정 준수 센터의 eDiscovery 사례와 연결된 보류 Microsoft 365 있는 모든 참가자의 사서함에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="dc5f8-108">이 콘텐츠는 참가자의 사서함에 복구 **가능한 항목** 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="dc5f8-109">보류 중인 사서함에 보존된 파일은 인덱싱되고 따라서 참가자의 사서함을 검색할 때 보안 준수 센터에서 Content Search를 실행하는 경우 검색할 &amp; 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="dc5f8-110">그러나 30MB보다 큰 첨부 파일은 둘 이상의 작은 파일로 분할되어 압축된(.zip) 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="dc5f8-111">이러한  *작은*  파일의 콘텐츠는 검색을 위해 인덱싱되지 않습니다. 콘텐츠 검색에서 반환되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="dc5f8-112">그러나 이러한  파일의 메타데이터(예: 파일 이름 및 작성자)는 검색을 위해 인덱싱됩니다. 콘텐츠 검색에서 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dc5f8-113">사서함에 대한 MaxReceiveSize 및 MaxSendSize 설정은 Exchange Online 모임에서 큰 파일을 유지하는 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="dc5f8-114">MaxReceiveSize 및 MaxSendSize의 기본 설정은 각각 36MB 및 35MB입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="dc5f8-115">그러나 이러한 기본 설정은 30MB보다 큰 비즈니스용 Skype 모임에서 파일을 보존하기에는 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="dc5f8-116">이는 Exchange Online 첨부 파일 및 기타 이진 데이터의 Base64 인코딩을 사용하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="dc5f8-117">메시지를 인코딩하면 크기가 약 33% 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="dc5f8-118">따라서 모임의 큰 파일을 비즈니스용 Skype 유지하려면 보류된 사용자의 경우 MaxReceiveSize 및 MaxSendSize의 값을 39MB(이전에 설명한 30MB 크기 제한보다 약 33%)로 늘리는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="dc5f8-119">그렇지 않으면 모임에 연결된 비즈니스용 Skype 유지되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="dc5f8-120">PowerShell에서 **Set-사서함 -MaxReceiveSize** 및 **Set-사서함 -maxSendSize** 명령을 사용하는 Exchange Online 자세한 내용은 Set-사서함 을 [참조하세요.](/powershell/module/exchange/mailboxes/Set-Mailbox)</span><span class="sxs-lookup"><span data-stu-id="dc5f8-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="dc5f8-121">보류 중이 아닌 사서함에는 모임 데이터가 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="dc5f8-122">예를 들어 두 참가자의 사서함이 보존으로 표시된 3인용 모임에서 모임 데이터는 해당 두 참가자의 사서함에 저장되지만 사서함이 보류 중이 아닌 세 번째 참가자의 사서함에는 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc5f8-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dc5f8-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="dc5f8-123">Related topics</span></span>
[<span data-ttu-id="dc5f8-124">사용자 지정 외부 액세스 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="dc5f8-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="dc5f8-125">지점 및 지점 파일 전송 차단</span><span class="sxs-lookup"><span data-stu-id="dc5f8-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="dc5f8-126">조직의 클라이언트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="dc5f8-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="dc5f8-127">조직에서 회의 정책 설정</span><span class="sxs-lookup"><span data-stu-id="dc5f8-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
