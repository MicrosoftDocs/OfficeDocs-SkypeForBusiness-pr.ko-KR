---
title: Skype 룸 시스템 비즈니스용 Skype 소프트웨어 라이선스
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 이 항목을 통해 비즈니스용 Skype 소프트웨어 볼륨 라이선스가 있는지 여부를 확인할 수 있습니다.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833928"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 룸 시스템: 비즈니스용 Skype 소프트웨어 라이선스
 
이 항목을 통해 비즈니스용 Skype 소프트웨어 볼륨 라이선스가 있는지 여부를 확인할 수 있습니다. 
  
Skype 룸 시스템은 소프트웨어 볼륨 라이선스가 필요한 설치된 비즈니스용 Skype 클라이언트를 사용 합니다. 첫 번째 Skype 룸 시스템을 배포하기 전에 KMS(키 관리 서버) 또는 MAK(복수 정품 인증 키)를 사용하여 배포의 볼륨 라이선스 상태를 확인합니다.
  
## <a name="key-management-servers-kms"></a>KMS(키 관리 서버)

KMS가 준비되어 있으며 비즈니스용 Skype 볼륨 라이선스 정품 인증을 배포할 경우 Skype 룸 시스템은 비즈니스용 Skype 클라이언트를 자동으로 정품 인증합니다. KMS가 현재 사용 중이지 않습니다.
  
명령 프롬프트에서 다음을 실행합니다.  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
자세한 내용은 DNS를 통해 Office 및 Windows KMS 호스트를 검색하고 권한이 없는 인스턴스를 제거하는 [방법을 참조하세요.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx) 
  
KMS를 설정하는 경우 [Office 2013의 KMS](https://technet.microsoft.com/library/ee624357.aspx) 정품 인증 및 Office 2013의 Active Directory 정품 인증에 대한 [OFFICE 2013 및 GVLK의 KMS](https://technet.microsoft.com/library/dn385360.aspx) 정품 인증을 참조합니다.
  
Lync용 Office 2013 일반 볼륨 라이선스 키: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R(이 키는 Skype 채팅방 시스템에서 네트워크의 KMS를 검색하게 합니다.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>VLSC(볼륨 라이선스 서비스 센터)의 MAK(복수 정품 인증 키)

고객이 다른 볼륨 라이선스 소프트웨어를 사용하는 경우 IT 부서는 VLSC를 사용하여 소프트웨어 정품 인증 및 VLA(볼륨 사용권 계약)를 관리합니다. 이렇게 하면 회사에서 비즈니스용 Skype VL 정품 인증을 구매할 수 있습니다. 이후에는 Skype 룸 시스템 관리 콘솔에서 입력을 위한 MAK를 얻을 수 있습니다.
  
VLA를 사용하는 고객은 계약을 관리하고 MAK를 얻는 데 사용되는 VLSC 자격 증명을 알아야 합니다. 불확실한 경우 고객의 재무 부서에서 고객이 VLA에 대해 지불한 금액을 확인할 수 있습니다.
  
MAK를 얻하려면 볼륨 라이선스 서비스 센터에 액세스하여 계약을 보고 MAK(제품 키)를 다운로드합니다. 자세한 내용은 볼륨 라이선스 서비스 센터로 [이동하세요.](https://www.microsoft.com/Licensing/servicecenter/default.aspx) 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a>VLSC 액세스 없이 Microsoft 365 또는 Office 365용 MAK

고객에게 볼륨 라이선스 계약이 없는 경우 비즈니스용 Skype 정품 인증을 관리하기가 훨씬 더 어렵습니다. 그러나 VLSC 액세스 권한이 없는 Microsoft 365 및 Office 365 고객은 Skype 룸 시스템을 판매하는 OEM에 다음 정보를 제공하여 홍보 MAK를 얻을 수 있습니다.
  
- 회사명
    
- 배포 연락처 이름, 전자 메일 및 전화 번호
    
- 배포된 시스템 수
    
- 배포 날짜
    
- 고객에게 Microsoft 기술 계정 관리자가 있는 경우 TAM의 이름 및 연락처 정보
    

