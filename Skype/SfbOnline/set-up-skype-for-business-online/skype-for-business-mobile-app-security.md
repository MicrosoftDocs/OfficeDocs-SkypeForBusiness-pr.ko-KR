---
title: 비즈니스용 Skype 모바일 앱 보안
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
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
description: '사용자에 대한 모바일 앱 보안을 설정하는 방법을 배워야 합니다. '
ms.openlocfilehash: 2c22f384196f0f05ca89d6f0e07ae84a1548d78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010781"
---
# <a name="skype-for-business-mobile-app-security"></a>비즈니스용 Skype 모바일 앱 보안

## <a name="skype-for-business-client-security"></a>비즈니스용 Skype 클라이언트 보안

이 문서에서는 비즈니스용 Skype Mobile Apps의 데이터 암호화 정보를 다 사용합니다.
  
|||||
|:-----|:-----|:-----|:-----|
||**사용자 이름/암호** <br/> |**앱 데이터(대화, <br/> 연락처 목록, 모임)** <br/> |**진단 로그** <br/> |
|**Android** <br/> |Android 계정에 자격 증명 정보를 저장합니다. 또한 계정으로 저장하기 전에 자격 증명을 암호화합니다. 암호화에 **"AES/CBC/PKCS5Padding"** 알고리즘을 사용합니다. <br/> |[sqlcipher라는](https://www.zetetic.net/sqlcipher/design/)라이브러리를 사용하여 암호화된 SQL 데이터베이스에 저장합니다. CBC 모드에서 256비트 AES의 기본 알고리즘을 사용합니다. 미사일 데이터는 항상 데이터베이스 파일에서 암호화되며 앱의 휘발성 메모리 및 호출 스택 내부에서만 전송 중 암호화되지 않습니다. 또한 사용자의 이름 및 암호 암호화와 동일한 방법을 사용하여 음성 파일을 암호화합니다(DB에 저장되지 않습니다). 음성 파일은 재생을 허용하기 위해 디스크에서 일시적으로 암호화되지 않습니다.  <br/> |이 정보는 암호화되지 않습니다.  <br/> |
|**iOS** <br/> |키체인에서 사용자 이름/암호를 암호화하지 않습니다. 그러나 키체인은 자체 암호화됩니다.  <br/> |앱 저장소의 모든 파일에 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 데이터 보호 플래그를 이미 사용하고 있습니다. 즉, 사용자가 디바이스를 재부팅한 후 처음으로 디바이스를 잠금 해제할 때까지 앱 저장소의 파일이 암호화됩니다. <br/> |이 정보는 암호화되지 않습니다.  <br/> |
|**Windows Phone** <br/> |Windows Phone은 Windows에서 DPAPI(데이터 보호 API)를 사용하여 암호를 보호합니다. 사용되는 암호화 체계는 AES입니다. Windows는 키 크기(또는 구성표)를 구성하는 옵션을 제공하지 않습니다. 따라서 DPAPI가 제공하는 모든 옵션입니다. 디바이스 TPM을 사용하여 사용자 및 디바이스에 특정된 키를 보호합니다. DPAPI 키는 앱에 국한되지 않습니다.  <br/> |WP 앱 데이터는 creds처럼 [DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I로 보호됩니다. 원하는 세부 정보에 따라 앱 데이터에 대한 일부 인덱스 정보는 (비 DPAPI) AES 암호화를 통해 보호되어 솔트 처리를 방지합니다. 따라서 암호 해독 없이 검색할 수 있으며 해당 키는 DPAPI로 보호됩니다. 캐시된 데이터는 데이터 폴더에 도달할 수 있는 경우 동일한 휴대폰에서 모든 프로세스에서 읽을 수 있습니다. Windows 암호화는 샌드박스 위반으로부터 보호하지 않습니다. 외부 액세스 시도만 보호합니다.  <br/> |이 정보는 암호화되지 않습니다.  <br/> |
   
**참고:** 위의 각 [모바일 플랫폼에서](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 사용할 수 있는 디바이스 핀 적용에 대한 공용 설명서를 참조하세요.
  
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
