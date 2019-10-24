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
f1keywords: None
ms.custom:
- Setup
description: '사용자를 위해 모바일 앱 보안을 설정 하는 방법을 알아봅니다. '
ms.openlocfilehash: 109fd6cb2ddccbc69ddae3e912506836ee49a399
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642570"
---
# <a name="skype-for-business-mobile-app-security"></a>비즈니스용 Skype 모바일 앱 보안

## <a name="skype-for-business-client-security"></a>비즈니스용 Skype 클라이언트 보안

이 문서에서는 비즈니스용 Skype 모바일 앱의 데이터 암호화 정보에 대해 설명 합니다.
  
|||||
|:-----|:-----|:-----|:-----|
||**사용자 이름/비밀 번호** <br/> |**앱 데이터 (대화,<br/> 연락처 목록, 모임)** <br/> |**진단 로그** <br/> |
|**Android** <br/> |Android 계정에 자격 증명 정보를 저장 합니다. 또한 자격 증명을 계정에 저장 하기 전에 암호화 합니다. 암호화에 " **AES/cbc-mac/PKCS5Padding** " 알고리즘을 사용 합니다. <br/> |[Sqlcipher](https://www.zetetic.net/sqlcipher/design/)라는 라이브러리를 사용 하 여 암호화 된 SQL 데이터베이스에 저장 합니다. CBC 모드에서 기본 알고리즘의 256 비트 AES를 사용 합니다. Rest의 데이터는 항상 데이터베이스 파일에서 암호화 되며 앱의 휘발성 메모리와 호출 스택 내부에서는 암호화 되지 않은 상태로 전송 됩니다. 또한 사용자의 이름 및 암호 암호화와 같은 방법을 사용 하 여 보이스 메일 파일을 암호화 합니다 (DB에 저장 되지 않음). 보이스 메일는 디스크에서 일시적으로 암호화 되지 않아 재생을 허용 합니다.  <br/> |이 정보는 암호화 되어 있지 않습니다.  <br/> |
|**Io** <br/> |키 집합의 사용자 이름/암호는 암호화 하지 않습니다. 그러나 키 집합이 암호화 됩니다.  <br/> |앱 저장소의 모든 파일에 대해 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection 플래그를 이미 사용 중입니다. 즉, 장치를 다시 부팅 한 후 사용자가 처음으로 장치를 잠금 해제할 때까지 앱 저장소의 파일이 암호화 됩니다. <br/> |이 정보는 암호화 되어 있지 않습니다.  <br/> |
|**Windows Phone** <br/> |Windows Phone은 Windows에서 DPAPI (Data Protection API)를 사용 하 여 암호를 보호 합니다. 사용 된 암호화 체계가 AES 라고 생각 합니다. Windows는 키 크기 (또는 구성표)를 구성 하는 옵션을 제공 하지 않으므로 DPAPI가 제공 하는 것입니다. 장치 TPM을 사용 하 여 사용자 및 디바이스와 관련 된 키를 보호 합니다. DPAPI 키가 앱과 관련이 없다는 점에 유의 하세요.  <br/> |WP 앱 데이터는 자격 증명 등의 [Dpap](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I로 보호 됩니다. 사용할 세부 정보에 따라 앱 데이터에 대 한 일부 인덱스 정보는 솔트을 방지 하기 위해 (DPAPI가 아닌) AES 암호화로 보호 되므로 암호를 해독 하지 않고 조회할 수 있으며 해당 키가 DPAPI로 보호 됩니다. 데이터 폴더에 도달할 수 있다고 가정 하 여 동일한 전화의 모든 프로세스가 캐시 된 데이터를 읽을 수 있습니다. Windows 암호화는 샌드박스 위반, 외부 액세스 시도만 보호 합니다.  <br/> |이 정보는 암호화 되어 있지 않습니다.  <br/> |
   
**참고:** 위의 각 모바일 플랫폼에서 사용할 수 있는 장치 pin 적용에 대 한 [이 공개 문서](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 를 참조 하세요.
  
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype Online 설정](set-up-skype-for-business-online.md)

[비즈니스용 Skype 사용자가 Skype 연락처를 추가 하도록 허용](let-skype-for-business-users-add-skype-contacts.md)

  
 
