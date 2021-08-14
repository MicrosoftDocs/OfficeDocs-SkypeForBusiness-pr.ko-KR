---
title: Office Web Apps Server 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 새 웹 Office Web Apps 서버 정의 마법사는 배포에 Office Web Apps Server의 새 웹앱 서버를 정의합니다. 다음 정보를 입력합니다.
ms.openlocfilehash: e72ff910b0ad299de9bbd5599aa64c338531024d0c1a41182567a67c8373ec3d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343602"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps Server 추가

새 **웹 Office Web Apps 서버** 정의 마법사는 배포에 Office 새 웹앱 서버를 정의합니다. 다음 정보를 입력합니다.

 **Office Web Apps 서버 FQDN:** 웹앱 서버를 호스팅할 서버의 Office 이름을 입력합니다.

 **Office Web Apps 서버** 검색 URL: 웹앱 서버의 전체 URL(uniform resource Locator)Office 입력합니다.

> [!TIP]
> Office Web Apps 서버 검색 URL의 기본 동작은 Office Web Apps 서버의 FQDN을 기반으로 하는 **URL을** 만드는 것입니다. `https://<FQDN of the Office Web Apps Server/hosting/discovery` 대부분의 경우에는 기본 형식을 변경할 필요가 없습니다. 웹앱 서버 및 Office Web Apps 서버 검색 URL이 달라야 Office 기본 형식을 변경해야 할 수 있습니다. 예를 들어 Office Web Apps 서버는 경계 네트워크에 배치되어 있으며 위치에 따라 다른 URL을 하게 됩니다.

 **Office Web Apps 서버가** 외부 네트워크(경계/인터넷)에 배포되어 있습니다. Office Web Apps 서버가 경계 네트워크, 외부 네트워크 또는 내부 네트워크와 다른 기타 네트워크 영역과 같은 내부 방화벽 외부에 있는 경우 확인란을 선택합니다.

## <a name="see-also"></a>참고 항목

[회의의 구성 요소 및 토폴로지](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)