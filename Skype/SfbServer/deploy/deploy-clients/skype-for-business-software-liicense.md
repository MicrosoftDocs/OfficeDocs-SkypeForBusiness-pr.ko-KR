---
title: Skype 채팅방 시스템 비즈니스용 Skype 소프트웨어 라이선스
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: 비즈니스용 Skype 소프트웨어 볼륨 라이선스가 있는지 확인 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: d1d04dc6c80d4e7e04b6ed7a946dfc393a308933
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190998"
---
# <a name="skype-room-system-skype-for-business-software-license"></a>Skype 대화방 시스템: 비즈니스용 Skype 소프트웨어 라이선스
 
비즈니스용 Skype 소프트웨어 볼륨 라이선스가 있는지 확인 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요. 
  
Skype 채팅방 시스템은 설치 된 비즈니스용 Skype 클라이언트를 사용 하며,이는 소프트웨어 볼륨 라이센스가 필요 합니다. 첫 번째 Skype 대화방 시스템을 배포 하기 전에 KMS (키 관리 서버) 또는 MAK (복수 정품 인증 키)를 사용 하 여 배포의 볼륨 라이선스 상태를 확인 합니다.
  
## <a name="key-management-servers-kms"></a>KMS (키 관리 서버)

KMS가 있고 비즈니스용 Skype 볼륨 라이선스 정품 인증을 배포 하는 경우 Skype 대화방 시스템은 비즈니스용 Skype 클라이언트를 자동으로 정품 인증 합니다. KMS의 현재 위치를 확인 하려면 다음을 수행 합니다.
  
명령 프롬프트에서 다음을 실행 합니다.`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`
  
자세한 내용은 [DNS를 통해 Office 및 WINDOWS KMS 호스트를 찾고 승인 되지 않은 인스턴스를 제거 하는 방법을](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)참조 하세요. 
  
KMS를 설정 하려면 Office 2013 및 GVLKs의 [kms 정품 인증](https://technet.microsoft.com/library/ee624357.aspx) [및 Office 2013의 Active Directory 정품 인증](https://technet.microsoft.com/library/dn385360.aspx) 을 참조 하세요.
  
Lync에 대 한 Office 2013 일반 볼륨 라이선스 키: 2MG3G BNTT-3MFW9-KDQW3-TCK7R (이 키로 인해 Skype 대화방 시스템에서 네트워크에서 KMS를 찾을 수 있습니다.)
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a>볼륨 라이선스 서비스 센터 (VLSC)의 MAK (복수 정품 인증 키)

고객이 다른 볼륨 라이선스 소프트웨어를 사용 하는 경우 IT 부서는 VLSC를 사용 하 여 소프트웨어 정품 인증 및 볼륨 라이선스 계약 (VLA)을 관리 합니다. 이렇게 하면 회사가 비즈니스용 Skype VL 정품 인증을 구매할 수 있으며 그 후에는 회사에서 Skype 채팅방 시스템 관리 콘솔의 입력에 대 한 MAK를 얻을 수 있습니다.
  
VLA가 있는 고객은 계약을 관리 하 고 MAK를 구하는 데 사용 되는 VLSC 자격 증명을 알아야 합니다. 모르는 경우 고객의 재무 부서가 고객이 VLA에 대해 지불 되었는지 확인할 수 있습니다.
  
MAK를 얻으려면 볼륨 라이선싱 서비스 센터에 액세스 하 여 규약을 보고 제품 키 (MAK)를 다운로드 합니다. 자세한 내용은 [볼륨 라이선싱 서비스 센터로](https://www.microsoft.com/Licensing/servicecenter/default.aspx)이동 하세요. 
  
## <a name="mak-for-office-365-without-vlsc-access"></a>VLSC 액세스 권한이 없는 Office 365의 MAK

고객이 볼륨 라이선스 계약서를 보유 하 고 있지 않은 경우 비즈니스용 Skype 정품 인증을 관리 하기가 훨씬 어렵습니다. 그러나 VLSC 없는 Office 365 고객은 Skype 대화방 시스템을 판매 하는 OEM에 다음 정보를 제공 하 여 판촉 MAK를 구할 수 있습니다.
  
- 회사 이름
    
- 배포 연락처 이름, 전자 메일 및 전화 번호
    
- 배포 된 시스템 수
    
- 배포 날짜
    
- 고객에 게 Microsoft 기술 계정 관리자가 있는 경우 TAM의 이름 및 연락처 정보
    

