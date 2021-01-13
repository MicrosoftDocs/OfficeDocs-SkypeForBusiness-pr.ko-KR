---
title: 비즈니스용 Skype 서버에서 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '요약: 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성하는 방법을 알아보십시오.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828038"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 참가 페이지 구성
 
**요약:** 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성하는 방법을 알아보십시오.
  
사용자가 모임 요청에서 모임 링크를 클릭하면 모임 참가 페이지에서 사용자의 컴퓨터에 비즈니스용 Skype 클라이언트가 이미 설치되어 있는지 여부를 검색합니다. 클라이언트가 이미 설치된 경우 클라이언트가 열리고 모임에 참가합니다. 클라이언트가 설치되어 있지 않은 경우 기본적으로 비즈니스용 Skype 클라이언트가 열립니다. 
  
## <a name="configure-the-meeting-join-page"></a>모임 참가 페이지 구성

사용자가 다른 버전의 클라이언트와 모임에 참가하도록 허용하려는 경우 모임 참가 페이지의 동작을 수정할 수 있습니다. 이러한 구성 옵션은 비즈니스용 Skype 서버 제어판에서 제거했지만 이 cmdlet을 사용하여 Set-CsWebServiceConfiguration 구성합니다.
  
**모임 참가 페이지 Set-CsWebServiceConfiguration 매개 변수**

|**Set-CsWebServiceConfiguration 매개 변수**|**설명**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |이 매개 변수는 비즈니스용 Skype 서버의 On-프레미스 버전에서 더는 사용되지 않습니다.  <br/> True로 설정하면 비즈니스용 Skype가 다른 클라이언트 응용 프로그램을 사용하여 모임에 참가하는 사용자에게 현재 클라이언트 응용 프로그램을 사용하여 모임에 참가할 수 있는 기회가 부여됩니다. 기본값은 False입니다.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |이 매개 변수는 비즈니스용 Skype 서버의 On-프레미스 버전에서 더는 사용되지 않습니다.  <br/>  True로 설정하면 온라인 회의 참가를 위한 대체 옵션이 자동으로 확장되어 사용자에게 표시됩니다. False(기본값)로 설정하면 이러한 옵션을 사용할 수 있지만 사용자가 직접 옵션 목록을 표시해야 합니다.  <br/> |
   

