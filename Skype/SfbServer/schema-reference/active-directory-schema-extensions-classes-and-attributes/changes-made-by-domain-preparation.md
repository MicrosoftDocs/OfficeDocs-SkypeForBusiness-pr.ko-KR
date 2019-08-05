---
title: 비즈니스용 Skype 서버에서 도메인 준비에의 한 변경 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 다음 표에는 도메인 준비에서 도메인 루트에 만드는 Ace (액세스 제어 항목)가 나열 되어 있습니다. 다른 언급이 없는 한 모든 Ace는 상속 됩니다.
ms.openlocfilehash: afd6747590e09b0b86b42119ad34eb26eaf9d8db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196816"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 도메인 준비에의 한 변경 사항
 
다음 표에는 도메인 준비에서 도메인 루트에 만드는 Ace (액세스 제어 항목)가 나열 되어 있습니다. 다른 언급이 없는 한 모든 Ace는 상속 됩니다.
  
**도메인 루트에 추가 된 Ace**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal 서비스**|**인증 된 사용자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|컨테이너 읽기 (상속 되지 않음)  <br/> |**'** <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet 사용자 계정 제한 사항 읽기  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet 개인 정보 읽기  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet 일반 정보 읽기  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet 공개 정보 읽기  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|PropertySet 사용자 읽기 RTCUserSearchProperty-설정  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |**'** <br/> |
|사용자 PropertySet RTCPropertySet 읽기  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 속성 프록시-주소 쓰기  <br/> |아니요  <br/> |아니요  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |
|PropertySet 사용자 쓰기 RTCUserSearchProperty-설정  <br/> |아니요  <br/> |아니요  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet RTCPropertySet에 쓰기  <br/> |아니요  <br/> |아니요  <br/> |**'** <br/> |아니요  <br/> |아니요  <br/> |
|PropertySet 읽기-모든 Active Directory 개체의 가져오기-복제-변경  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |**'** <br/> |아니요  <br/> |
   
다음 표에는 세 가지 기본 제공 컨테이너 (사용자, 컴퓨터 및 도메인 컨트롤러)에서 도메인 준비가 만드는 Ace가 나열 되어 있습니다. 다른 언급이 없는 한 모든 Ace는 상속 됩니다.
**기본 제공 컨테이너에 Ace가 추가 됨**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|컨테이너 읽기 (상속 되지 않음)  <br/> |**'** <br/> |**'** <br/> |
   

