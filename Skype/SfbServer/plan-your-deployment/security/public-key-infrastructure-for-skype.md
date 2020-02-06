---
title: 비즈니스용 Skype 서버용 공개 키 인프라
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: 비즈니스용 Skype 서버는 서버 인증용 인증서를 사용 하 고 클라이언트와 서버 간 및 여러 서버 역할 간에 신뢰 체인을 설정 합니다. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 및 Windows Server 2008 PKI (공개 키 인프라)는이 신뢰 체인을 설정 하 고 유효성을 검사 하기 위한 인프라를 제공 합니다.
ms.openlocfilehash: ec2ae6e94d9cf00a6193c45d6cefd7db6d5a5b62
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815636"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 공개 키 인프라
 
비즈니스용 Skype 서버는 서버 인증용 인증서를 사용 하 고 클라이언트와 서버 간 및 여러 서버 역할 간에 신뢰 체인을 설정 합니다. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 및 Windows Server 2008 PKI (공개 키 인프라)는이 신뢰 체인을 설정 하 고 유효성을 검사 하기 위한 인프라를 제공 합니다.
  
인증서는 디지털 Id입니다. 이름으로 서버를 식별 하 고 해당 속성을 지정 합니다. 인증서에 대 한 정보가 유효한 지 확인 하려면 클라이언트 또는 서버에 연결 되는 다른 서버에서 신뢰 하는 CA에서 인증서를 발급 해야 합니다. 서버가 개인 네트워크의 다른 클라이언트 및 서버와만 연결 하는 경우 엔터프라이즈 CA가 될 수 있습니다. 서버가 개인 네트워크 외부의 엔터티와 상호 작용 하는 경우 공용 CA가 필요할 수 있습니다.
  
인증서에 대 한 정보가 유효 하더라도 인증서를 제시 하는 서버가 실제로 인증서로 표시 되는 것을 확인 하는 방법이 있어야 합니다. 여기에는 Windows PKI가 제공 됩니다.
  
각 인증서는 공개 키에 연결 되어 있습니다. 인증서에 명명 된 서버에는 해당 하는 해당 개인 키가 저장 되어 있습니다. 연결 하는 클라이언트나 서버는 공개 키를 사용 하 여 임의의 정보를 암호화 하 고 서버에 보냅니다. 서버에서 정보를 해독 하 고 일반 텍스트로 반환 하는 경우 연결 엔터티에서 서버는 인증서에 대 한 개인 키를 보유 하 고 있으므로 인증서에 이름이 지정 된 서버 인지 확인할 수 있습니다.
  
> [!NOTE]
> 모든 공개 Ca가 비즈니스용 Skype 서버 인증서의 요구 사항을 준수 하지는 않습니다. 공개 인증서 요구 사항에 대 한 인증 된 공개 CA 공급 업체 목록을 참조 하는 것이 좋습니다. 자세한 내용은 [통합 커뮤니케이션 인증서 파트너](https://go.microsoft.com/fwlink/p/?LinkId=140898)를 참조 하세요. 
  
## <a name="crl-distribution-points"></a>CRL 배포 지점

비즈니스용 Skype Server에는 모든 서버 인증서에 CRL (인증서 해지 목록) 배포 지점이 하나 이상 포함 되어 있어야 합니다. Cdp (CRL 배포 지점)는 발급 된 시간 이후 인증서가 해지 되지 않았음을 확인 하 고 인증서가 유효 기간 내에 있는 경우 Crl을 다운로드할 수 있는 위치입니다. CRL 배포 지점은 인증서의 속성에 URL로 기록 되며 일반적으로 HTTP를 통해 보호 됩니다.
  
## <a name="enhanced-key-usage"></a>향상 된 키 사용

서버 인증을 위해 비즈니스용 Skype Server에는 EKU (확장 된 키 사용)를 지원 하기 위해 모든 서버 인증서가 필요 합니다. 서버 인증에 대 한 EKU 필드를 구성 하는 것은 인증서가 서버 인증 목적으로 유효 하다는 것을 의미 합니다. 이 EKU는 MTLS에 필수적입니다. EKU에 두 개 이상의 항목이 있는 경우 인증서를 두 가지 용도로 사용할 수 있습니다.
  

