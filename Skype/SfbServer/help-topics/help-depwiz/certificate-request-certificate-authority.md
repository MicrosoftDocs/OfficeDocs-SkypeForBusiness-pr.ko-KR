---
title: 인증서 요청(인증 기관)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: CA(인증 기관) 선택 페이지에서 온라인 CA(인증 기관)(일반적으로 내부 네트워크에 있는 서버)에 인증서를 요청할 때 다음과 같은 두 가지 옵션이 제공됩니다.
ms.openlocfilehash: b70daa9a4b9a212d770176b652e3ac70b7149c4e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823892"
---
# <a name="certificate-request-certificate-authority"></a>인증서 요청(인증 기관)
 
**CA(인증 기관) 선택** 페이지에서 온라인 CA(인증 기관)(일반적으로 내부 네트워크에 있는 서버)에 인증서를 요청할 때 다음과 같은 두 가지 옵션이 제공됩니다.
  
1. 환경에서 감지된 목록에서 CA 선택
    
2. 다른 인증 기관 지정
    
첫 번째 옵션을 선택 하면 환경에서 검색 된 모든 Windows Server 기반 인증 기관이 포함 된 드롭다운 목록이 표시 됩니다. 인증서에 적합한 인증 기관을 선택합니다. 선택해야 하는 CA를 확인하려면 CA 관리자에게 문의해야 할 수 있습니다.
  
두 번째 옵션을 선택하는 경우 인증서에 사용할 인증 기관의 FQDN(정규화된 도메인 이름) 및 CA 인스턴스를 입력합니다. 이 옵션은 사용하려는 CA가 Windows Server 기반 CA는 아닌 경우에 적합하지만, Windows Server 기반 CA에 대해서도 작동합니다.
  
> [!IMPORTANT]
> 인증서 요청을 정상적으로 수행하는 데 필요한 그룹 구성원 자격을 확인해야 합니다. 일반적으로 인증 기관에는 서버에 비즈니스용 Skype 서버를 설치 하기 위한 요구 사항 으로부터 서로 다른 사용 권한 요구 사항이 있습니다. CA 관리자에게 인증서를 요청하기 위한 요구 사항을 확인하세요. 
  

