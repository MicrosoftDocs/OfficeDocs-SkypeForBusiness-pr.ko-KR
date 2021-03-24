---
title: 비즈니스용 Skype 모임에 연결된 큰 파일 보존
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
description: 비즈니스용 Skype 모임에 파일을 첨부한 다음 참가자가 열고 다운로드할 수 있습니다. 비즈니스용 Skype 모임에 연결된 파일은 사서함이 소송 보류에 배치되거나 Microsoft 365 또는 Office 365 보존 정책이 적용되거나 Microsoft 365 준수 센터의 eDiscovery 사례와 연결된 보류에 배치된 모든 참가자의 사서함에 보관됩니다. 이 콘텐츠는 참가자의 사서함에 복구 가능한 항목 폴더에 저장됩니다.
ms.openlocfilehash: 515f8b68db04a7acfc8eab2d7c639157cdb0da8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100574"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>비즈니스용 Skype 모임에 연결된 큰 파일 보존

비즈니스용 Skype 모임에 파일을 첨부한 다음 참가자가 열고 다운로드할 수 있습니다. 비즈니스용 Skype 모임에 연결된 파일은 사서함이 소송 보류에 배치되거나 Microsoft 365 또는 Office 365 보존 정책이 적용되거나 Microsoft 365 준수 센터의 eDiscovery 사례와 연결된 보류에 배치된 모든 참가자의 사서함에 보관됩니다. 이 콘텐츠는 참가자의 사서함에 복구 **가능한 항목** 폴더에 저장됩니다.
  
보류 중인 사서함에 보존된 파일은 인덱싱되고 따라서 참가자의 사서함을 검색할 때 보안 준수 센터에서 Content Search를 실행하는 경우 검색할 &amp; 수 있습니다. 그러나 30MB보다 큰 첨부 파일은 둘 이상의 작은 파일로 분할되어 압축된 파일(.zip) 파일로 저장됩니다. 이러한  *작은*  파일의 콘텐츠는 검색을 위해 인덱싱되지 않습니다. 콘텐츠 검색에서 반환되지 않을 수 있습니다. 그러나 이러한  파일의 메타데이터(예: 파일 이름 및 작성자)는 검색을 위해 인덱싱됩니다. 콘텐츠 검색에서 반환될 수 있습니다.
  
> [!IMPORTANT]
> Exchange Online 사서함에 대한 MaxReceiveSize 및 MaxSendSize 설정은 비즈니스용 Skype 모임에서 대용량 파일을 유지하는 능력에 영향을 줄 수 있습니다. MaxReceiveSize 및 MaxSendSize의 기본 설정은 각각 36MB 및 35MB입니다. 그러나 이러한 기본 설정은 30MB보다 큰 비즈니스용 Skype 모임에서 파일을 보존하기에는 너무 작습니다. Exchange Online은 메시지 첨부 파일 및 기타 이진 데이터의 Base64 인코딩을 사용하기 때문에 이진 데이터를 사용할 수 있습니다. 메시지를 인코딩하면 크기가 약 33% 증가합니다. 따라서 비즈니스용 Skype 모임의 큰 파일이 유지되도록 하기 위해 보류된 사용자의 경우 MaxReceiveSize 및 MaxSendSize의 값을 39MB(이전에 설명한 30MB 크기 제한보다 약 33% 더 큰)로 늘리는 것이 좋습니다. 그렇지 않으면 비즈니스용 Skype 모임에 연결된 큰 파일이 유지되지 않을 수 있습니다. Exchange Online PowerShell에서 **Set-사서함 -MaxReceiveSize** 및 **Set-사서함 -MaxSendSize** 명령 사용에 대한 자세한 내용은 사서함 설정 을 [참조하세요.](/powershell/module/exchange/mailboxes/Set-Mailbox)
  
보류 중이 아닌 사서함에는 모임 데이터가 저장되지 않습니다. 예를 들어 두 참가자의 사서함이 보존으로 표시된 3인용 모임에서 모임 데이터는 해당 두 참가자의 사서함에 저장되지만 사서함이 보류 중이 아닌 세 번째 참가자의 사서함에는 저장되지 않습니다.
  
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[지점 및 지점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)
  
  
