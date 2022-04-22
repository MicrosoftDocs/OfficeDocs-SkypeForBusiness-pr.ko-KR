---
title: 비즈니스용 Skype 모임에 첨부된 대용량 파일 보존
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, v-tophillips
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 비즈니스용 Skype 모임에 파일을 첨부할 수 있습니다. 그러면 참가자가 열고 다운로드할 수 있습니다. 비즈니스용 Skype 모임에 첨부된 파일은 사서함이 소송 보존에 배치되거나, Microsoft 365 또는 Office 365 보존 정책이 적용되었거나, Microsoft Purview 규정 준수 포털의 eDiscovery 사례와 연결된 보류에 있는 모든 참가자의 사서함에 보존됩니다. 이 콘텐츠는 사서함에 있는 참가자의 복구 가능한 항목 폴더에 저장됩니다.
ms.openlocfilehash: b799c1a471ac3884aa1b22cc1a681e53ee8284e9
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031873"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>비즈니스용 Skype 모임에 첨부된 대용량 파일 보존

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

비즈니스용 Skype 모임에 파일을 첨부할 수 있습니다. 그러면 참가자가 열고 다운로드할 수 있습니다. 비즈니스용 Skype 모임에 첨부된 파일은 사서함이 소송 보존에 배치되거나, Microsoft 365 또는 Office 365 보존 정책이 적용되었거나, Microsoft Purview 규정 준수 포털의 eDiscovery 사례와 연결된 보류에 있는 모든 참가자의 사서함에 보존됩니다. 이 콘텐츠는 사서함에 있는 참가자의 **복구 가능한 항목** 폴더에 저장됩니다.
  
보류 중인 사서함에 보관된 파일은 인덱싱되므로 참가자의 사서함을 검색할 때 보안 &amp; 준수 센터에서 콘텐츠 검색을 실행할 때 검색할 수 있습니다. 그러나 30MB보다 큰 첨부 파일은 두 개 이상의 작은 파일로 분할되어 압축된(.zip) 파일로 저장됩니다. 이러한 작은 파일의  *콘텐츠*  는 검색을 위해 인덱싱되지 않으며 콘텐츠 검색에 반환되지 않을 수 있습니다. 그러나 이러한 파일의 *메타데이터*  (예: 파일 이름 및 작성자)는 검색을 위해 인덱싱되며 콘텐츠 검색에 반환될 수 있습니다.
  
> [!IMPORTANT]
> Exchange Online 사서함에 대한 MaxReceiveSize 및 MaxSendSize 설정은 비즈니스용 Skype 모임에서 대용량 파일을 유지하는 기능에 영향을 줄 수 있습니다. MaxReceiveSize 및 MaxSendSize의 기본 설정은 각각 36MB 및 35MB입니다. 그러나 이러한 기본 설정은 너무 작아서 30MB보다 큰 비즈니스용 Skype 모임의 파일을 보존할 수 없습니다. Exchange Online 메시지 첨부 파일 및 기타 이진 데이터의 Base64 인코딩을 사용하기 때문입니다. 메시지가 인코딩되면 해당 크기가 약 33% 증가합니다. 따라서 비즈니스용 Skype 모임의 대용량 파일이 유지되도록 하려면 보류 중인 사용자의 경우 MaxReceiveSize 및 MaxSendSize의 값을 39MB(이전에 설명한 30MB 크기 제한보다 약 33% 더 큰)로 늘리는 것이 좋습니다. 그렇지 않으면 비즈니스용 Skype 모임에 첨부된 대용량 파일이 보존되지 않을 수 있습니다. Exchange Online PowerShell에서 **Set-Mailbox -MaxReceiveSize** 및 **Set-Mailbox -MaxSendSize** 명령을 사용하는 방법에 대한 자세한 내용은 [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox)를 참조하세요.
  
보류되지 않은 사서함에는 모임 데이터가 저장되지 않습니다. 예를 들어 두 참가자의 사서함이 보존으로 표시된 3인 모임에서 모임 데이터는 해당 두 참가자의 사서함에 저장되지만 사서함이 보류되지 않은 세 번째 참가자의 사서함에는 저장되지 않습니다.
  
## <a name="related-topics"></a>관련 항목
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[지점 및 지점 간의 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)
  
  
