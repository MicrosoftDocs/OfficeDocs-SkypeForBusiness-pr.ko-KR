---
title: 도메인 준비에서 변경한 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 다음 표에는 도메인 준비가 도메인 루트에 대해 만든 ACE(액세스 제어 항목)가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.
ms.openlocfilehash: af84828aac349f4b09627d96d3a84cc97ff49a79
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630392"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>도메인 준비에서 변경한 비즈니스용 Skype 서버
 
다음 표에는 도메인 준비가 도메인 루트에 대해 만든 ACE(액세스 제어 항목)가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.
  
**도메인 루트에 추가된 ACE**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authenticated-Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|컨테이너 읽기(상속되지 않음)  <br/> |**예** <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet User-Account-Restrictions 읽기  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet Personal-Information 읽기  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet General-Information 읽기  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet Public-Information 읽기  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet RTCUserSearchProperty-Set 읽기  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |**예** <br/> |
|사용자 PropertySet RTCPropertySet 읽기  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|사용자 Property Proxy-Addresses 쓰기  <br/> |아니요  <br/> |아니요  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet RTCUserSearchProperty-Set 쓰기  <br/> |아니요  <br/> |아니요  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |
|사용자 PropertySet RTCPropertySet 쓰기  <br/> |아니요  <br/> |아니요  <br/> |**예** <br/> |아니요  <br/> |아니요  <br/> |
|모든 Active Directory 개체의 PropertySet DS-Replication-Get-Changes 읽기  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |**예** <br/> |아니요  <br/> |
   
다음 표에는 도메인 준비가 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 만드는 ACE가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.
**기본 제공 컨테이너에 추가된 AES**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|컨테이너 읽기(상속되지 않음)  <br/> |**예** <br/> |**예** <br/> |
   

