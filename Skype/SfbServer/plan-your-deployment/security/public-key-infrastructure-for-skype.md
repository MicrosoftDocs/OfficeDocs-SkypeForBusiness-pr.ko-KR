---
title: 관리용 공개 키 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: 비즈니스용 Skype 서버 인증서를 통해 서버 인증을 지원하고 클라이언트와 서버 간에 그리고 여러 서버 역할 간에 신뢰 체인을 설정해야 합니다. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 및 Windows Server 2008 PKI(공개 키 인프라)는 이 신뢰 체인을 설정하고 유효성을 검사하기 위한 인프라를 제공합니다.
ms.openlocfilehash: 7b955aa07143cead900a0140ac8ee64fa02ba34ed3945553e376123c7260909d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329492"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>관리용 공개 키 비즈니스용 Skype 서버
 
비즈니스용 Skype 서버 인증서를 통해 서버 인증을 지원하고 클라이언트와 서버 간에 그리고 여러 서버 역할 간에 신뢰 체인을 설정해야 합니다. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 및 Windows Server 2008 PKI(공개 키 인프라)는 이 신뢰 체인을 설정하고 유효성을 검사하기 위한 인프라를 제공합니다.
  
인증서는 디지털 ID입니다. 이름을 사용하여 서버를 식별하고 해당 속성을 지정합니다. 인증서에 대한 정보가 유효한지 확인하려면 클라이언트 또는 서버에 연결하는 다른 서버에서 신뢰하는 CA에서 인증서를 발급해야 합니다. 서버가 개인 네트워크의 다른 클라이언트 및 서버와만 연결되는 경우 CA는 엔터프라이즈 CA일 수 있습니다. 서버가 개인 네트워크 외부의 엔터티와 상호 작용하는 경우 공용 CA가 필요한 것일 수 있습니다.
  
인증서의 정보가 유효하더라도 인증서를 제공하는 서버가 실제로 인증서에 나와 있는 서버인지를 확인하는 방법이 있어야 합니다. 이를 위해 Windows PKI를 사용합니다.
  
각 인증서는 공개 키에 연결됩니다. 인증서에 이름이 지정되어 있는 서버는 다른 위치에서는 알 수 없는 해당 개인 키를 포함합니다. 이 서버에 연결하는 클라이언트 또는 서버는 공개 키를 사용하여 임의의 정보를 암호화한 다음 서버로 보냅니다. 서버에서 이 정보의 암호를 해독하여 일반 텍스트로 반환하면 연결 대상 엔터티는 해당 서버가 인증서의 개인 키를 포함하며 인증서에 이름이 나와 있는 서버임을 확인할 수 있습니다.
  
> [!NOTE]
> 모든 공용 CAS가 인증서의 요구 사항을 비즈니스용 Skype 서버 않습니다. 따라서 인증된 공용 CA 공급업체 목록을 참조하여 공용 인증서 요구 사항을 확인하는 것이 좋습니다. 자세한 내용은 [Unified Communications Certificate Partners을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=140898) 
  
## <a name="crl-distribution-points"></a>CRL 배포 지점

비즈니스용 Skype 서버 인증서에 하나 이상의 CRL(인증서 해지 목록) 배포 지점이 포함되어야 합니다. CDP(CRL 배포 지점)는 인증서 발급 시점 이후로 인증서가 해지되지 않았는지 그리고 인증서가 아직 유효 기간 내에 있는지 확인하기 위해 CRL을 다운로드할 수 있는 위치입니다. CRL 배포 지점은 인증서 속성에 URL로 기록되며 일반적으로 보안 HTTP입니다.
  
## <a name="enhanced-key-usage"></a>향상 키 사용

비즈니스용 Skype 서버 인증을 위해 모든 서버 인증서가 EKU(Enhanced Key Usage)를 지원해야 합니다. 서버 인증을 위해 EKU 필드를 구성하면 인증서를 서버 인증용으로 사용할 수 있습니다. 이 EKU는 MTLS에 필수적인 요소입니다. EKU에 여러 항목을 포함하여 인증서를 다양한 용도로 활용할 수 있습니다.
  

