---
title: 비즈니스용 Skype 서버에서 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '요약: 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818519"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모임 참가 페이지 구성
 
**요약:** 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성 하는 방법에 대해 알아봅니다.
  
사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 비즈니스용 Skype 클라이언트가 사용자의 컴퓨터에 이미 설치 되어 있는지 여부를 감지 합니다. 클라이언트가 이미 설치 된 경우에는 클라이언트가 모임을 열고 참가 합니다. 클라이언트가 설치 되어 있지 않으면 기본적으로 비즈니스용 Skype 클라이언트가 열립니다. 
  
## <a name="configure-the-meeting-join-page"></a>모임 참가 페이지 구성

사용자가 다른 버전의 클라이언트와 모임에 참가할 수 있도록 하려면 모임 참가 페이지의 동작을 수정할 수 있습니다. 이러한 구성 옵션은 비즈니스용 Skype Server 제어판에서 제거 되었지만 CsWebServiceConfiguration cmdlet을 사용 하 여 구성 합니다.
  
**모임 참가 페이지 집합-CsWebServiceConfiguration 매개 변수**

|**Set-CsWebServiceConfiguration 매개 변수**|**설명**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |이 매개 변수는 비즈니스용 Skype Server 온-프레미스 버전에서 사용할 때 사용 되지 않습니다.  <br/> True로 설정 하면 비즈니스용 Skype 외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 현재 클라이언트 응용 프로그램을 사용 하 여 모임에 참가할 수 있는 기회가 제공 됩니다. 기본값은 False입니다.  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |이 매개 변수는 비즈니스용 Skype Server 온-프레미스 버전에서 사용할 때 사용 되지 않습니다.  <br/>  True로 설정 하면 온라인 회의에 참가 하는 대체 옵션이 자동으로 확장 되어 사용자에 게 표시 됩니다. False (기본값)로 설정 하는 경우 이러한 옵션을 사용할 수 있지만, 사용자는 자신의 옵션 목록을 표시 해야 합니다.  <br/> |
   

