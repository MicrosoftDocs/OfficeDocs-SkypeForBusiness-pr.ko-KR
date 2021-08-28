---
title: 모임 참가 페이지에서 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '요약: 모임 참가 페이지에서 모임 참가 페이지를 구성하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: ba90c771321732956b38f5f07af10798829fc54f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587094"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>모임 참가 페이지에서 비즈니스용 Skype 서버
 
**요약:** 모임 참가 페이지에서 모임 참가 페이지를 구성하는 비즈니스용 Skype 서버.
  
사용자가 모임 요청에서 모임 링크를 클릭하면 모임 참가 페이지에서 비즈니스용 Skype 클라이언트가 사용자 컴퓨터에 이미 설치되어 있는지 여부를 검색합니다. 클라이언트가 이미 설치된 경우 클라이언트가 열리고 모임에 참가합니다. 클라이언트가 설치되어 있지 않은 경우 기본적으로 클라이언트 비즈니스용 Skype 열립니다. 
  
## <a name="configure-the-meeting-join-page"></a>모임 참가 페이지 구성

사용자가 다른 버전의 클라이언트와 모임에 참가하도록 허용하려는 경우 모임 참가 페이지의 동작을 수정할 수 있습니다. 이러한 구성 옵션은 비즈니스용 Skype 서버 제어판에서 제거했지만 Set-CsWebServiceConfiguration cmdlet을 사용하여 구성합니다.
  
**모임 참가 페이지 Set-CsWebServiceConfiguration 매개 변수**

|**Set-CsWebServiceConfiguration 매개 변수**|**설명**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |이 매개 변수는 프레미스 버전의 비즈니스용 Skype 서버.  <br/> True로 설정하면 다른 클라이언트 응용 프로그램을 사용하여 모임에 참가하는 비즈니스용 Skype 현재 클라이언트 응용 프로그램을 사용하여 모임에 참가할 수 있는 기회가 부여됩니다. 기본값은 False입니다.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |이 매개 변수는 프레미스 버전의 비즈니스용 Skype 서버.  <br/>  True로 설정하면 온라인 회의 참가를 위한 대체 옵션이 자동으로 확장되어 사용자에게 표시됩니다. False(기본값)로 설정하면 이러한 옵션을 사용할 수 있지만 사용자가 직접 옵션 목록을 표시해야 합니다.  <br/> |
   

