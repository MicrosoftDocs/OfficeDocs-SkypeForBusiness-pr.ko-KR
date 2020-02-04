---
title: 비즈니스용 Skype 모임에 첨부 된 대용량 파일 보존
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
description: 비즈니스용 Skype 모임에 파일을 첨부 하 고, 참가자가 열고 다운로드할 수 있습니다. 비즈니스용 Skype 모임에 첨부 된 파일은 사서함이 소송 보류에 저장 되어 있는 모든 참가자의 사서함에 보존 되며, Office 365 보존 정책이 적용 되거나, Office 365 보안 &amp; 준수 센터에서 eDiscovery 사례와 연결 된 보류에 배치 됩니다. 이 콘텐츠는 해당 사서함의 참석자의 복구 가능한 항목 폴더에 저장 됩니다.
ms.openlocfilehash: fdd6786cb9b7e5535abee47eb1f0b538b6a22b45
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706653"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>비즈니스용 Skype 모임에 첨부 된 대용량 파일 보존

비즈니스용 Skype 모임에 파일을 첨부 하 고, 참가자가 열고 다운로드할 수 있습니다. 비즈니스용 Skype 모임에 첨부 된 파일은 사서함이 소송 보류에 저장 되어 있는 모든 참가자의 사서함에 보존 되며, Office 365 보존 정책이 적용 되거나, Office 365 보안 &amp; 준수 센터에서 eDiscovery 사례와 연결 된 보류에 배치 됩니다. 이 콘텐츠는 해당 사서함의 참석자의 **복구 가능한 항목** 폴더에 저장 됩니다.
  
보류 중인 사서함에 유지 되는 파일은 인덱싱되어 있으므로 참가자의 사서함을 검색할 때 보안 &amp; 준수 센터에서 콘텐츠 검색을 실행할 때 검색 될 수 있습니다. 그러나 30mb 보다 더 많은 첨부 파일은 두 개 이상의 작은 파일로 나뉘어 압축 (.zip) 파일로 저장 됩니다. 이러한 작은 파일의 *콘텐츠* 는 검색을 위해 인덱싱되지 않으며 콘텐츠 검색에 반환 되지 않을 수 있습니다. 그러나 이러한 파일의 *메타 데이터* (예: 파일 이름 및 만든이)는 검색을 위해 인덱싱되어 있으며 콘텐츠 검색에 반환 될 수 있습니다.
  
> [!IMPORTANT]
> Exchange Online 사서함에 대 한 MaxReceiveSize 및 MaxSendSize 설정은 비즈니스용 Skype 모임에서 대용량 파일을 유지 하는 기능에 영향을 줄 수 있습니다. MaxReceiveSize 및 MaxSendSize에 대 한 기본 설정은 각각 36 MB 및 35 MB입니다. 그러나 이러한 기본 설정은 30 MB 보다 더 많은 비즈니스용 Skype 모임에서 파일을 보존 하기에는 너무 작아서 사용할 수 없습니다. 이는 Exchange Online에서 메시지 첨부 파일 및 다른 이진 데이터의 Base64 인코딩을 사용 하기 때문입니다. 메시지를 인코딩하면 약 33% 단위로 크기가 증가 합니다. 따라서 비즈니스용 Skype 모임의 대용량 파일이 유지 되도록 하려면 MaxReceiveSize 및 MaxSendSize에 대 한 값을 39 MB (이전에 설명 된 30mb의 크기 제한을 초과 하는 약 33% 큼)로 늘리는 것이 좋습니다. 보류 중인 사용자에 게 적용 됩니다. 그렇지 않으면 비즈니스용 Skype 모임에 연결 된 큰 파일이 보존 되지 않을 수 있습니다. Exchange Online PowerShell의 **set-MaxReceiveSize** 및 **Set-maxsendsize** 명령 사용에 대 한 자세한 내용은 [사서함 설정을](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)참조 하세요.
  
보류 중인 사서함에는 모임 데이터가 저장 되지 않습니다. 예를 들어 두 참가자의 사서함이 보존으로 표시 된 3 명 모임에서 모임 데이터는 해당 두 참가자의 사서함에 저장 되지만 세 번째 참가자의 사서함에는 저장 되지 않으며 사서함이 보류 되지 않은 것입니다.
  
## <a name="related-topics"></a>관련 주제
[사용자 지정 외부 액세스 정책 만들기](create-custom-external-access-policies.md)

[점 대 점 파일 전송 차단](block-point-to-point-file-transfers.md)

[조직의 클라이언트 정책 설정](set-up-client-policies-for-your-organization.md)

[조직에서 회의 정책 설정](set-up-conferencing-policies-for-your-organization.md)
  
  
 