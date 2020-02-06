---
title: 테스트 장치 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: 테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다. 테스트 장치를 테스트 장치 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가 하면 비즈니스용 Skype Server 제어판의 테스트 장치 페이지에 있는 목록에 표시 됩니다.
ms.openlocfilehash: e34a70091e4558db4c2e201f86c9aa81d50f3dda
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822060"
---
# <a name="test-device-create-new-or-edit-existing"></a>테스트 장치: 새로 만들기 또는 기존 항목 편집

테스트 장치 기능은 장치 업데이트 기능과 함께 작동합니다. 테스트 장치를 **테스트 장치** 페이지에 추가한 다음 이 장치를 사용하여 프로덕션 장치에 업데이트를 배포하기 전에 새 업데이트의 기능을 확인할 수 있습니다. 장치는 전역으로 테스트하거나(nm-server-w15-short 환경 전체에서) 단일 사이트에서 테스트할 수 있습니다. MAC(미디어 액세스 제어) 주소 또는 일련 번호로 테스트 장치를 식별합니다. 장치를 추가 하면 비즈니스용 Skype Server 제어판의 **테스트 장치** 페이지에 있는 목록에 표시 됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 테스트 장치** 또는 **테스트 장치 편집** 페이지에서 다음 작업을 수행할 수 있습니다.

- 새 테스트 장치 추가

- 기존 테스트 장치의 속성 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.

- **범위** 테스트 장치의 범위 (전역 또는 사이트)를 식별 합니다.

- **이름** 테스트 디바이스의 이름을 추가 하거나 수정할 수 있습니다.

- **장치 이름** 테스트 디바이스의 이름을 추가 하거나 수정할 수 있습니다.

- **식별자 형식** 다음 중 하나를 선택 하 여 장치를 식별 하는 데 사용할 방법을 선택할 수 있습니다.

  - **MAC 주소**

  - **일련 번호**

- **고유 식별자** 디바이스의 MAC 주소 또는 일련 번호를 입력할 수 있습니다.

장치를 테스트하는 방법에 대한 자세한 내용은 작업 설명서의 [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)를 참조하세요.
## <a name="see-also"></a>참고 항목

[장치 테스트](test-device.md)

[신규-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[조직의 디바이스에 대 한 소프트웨어 업데이트 보기](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
