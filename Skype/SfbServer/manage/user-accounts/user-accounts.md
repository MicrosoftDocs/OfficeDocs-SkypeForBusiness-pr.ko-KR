---
title: 비즈니스용 Skype 서버의 사용자 계정 관리
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 이 문서의 섹션에서는 비즈니스용 Skype 서버에서 Active Directory 사용자를 활성화, 일시적으로 사용하지 않도록 설정 또는 제거하는 방법을 설명합니다.
ms.openlocfilehash: aa1b1b21ba089815af20b61da3360179fb10935e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832778"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>비즈니스용 Skype 서버의 사용자 계정 관리

이 문서의 섹션에서는 비즈니스용 Skype 서버에서 Active Directory 사용자를 활성화, 일시적으로 사용하지 않도록 설정 또는 제거하는 방법을 설명합니다.

Active Directory 사용자를 사용하도록 설정하는 방법에 대한 자세한 내용은 새 사용자 계정 [만들기를 참조하십시오.](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx) Active Directory 사용자를 삭제하는 방법에 대한 자세한 내용은 사용자 계정 [삭제를 참조하십시오.](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)

이러한 절차는 비즈니스용 Skype 사용량이 가장 낮은 유지 관리 기간 동안 수행해야 합니다. 이 수행 여부는 조직의 요구에 따라 결정됩니다.

이 문서에는 다음 절차가 포함되어 있습니다.

- [한 명 이상의 사용자를 검색하려면](user-accounts.md#Search)

- [새 비즈니스용 Skype 서버 사용자 추가 및 사용](user-accounts.md#Add)

- [이전에 비즈니스용 Skype 서버에 대해 사용하도록 설정된 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정](user-accounts.md#Disable)

- [사용자를 사용하지 않도록 Enterprise Voice](user-accounts.md#Disable_EV)

- [비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 계정 제거](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>한 명 이상의 사용자를 검색하려면
<a name="Search"> </a>

검색 쿼리 결과를 사용하여 비즈니스용 Skype 서버에 대한 Active Directory 사용자를 구성할 수 있습니다. 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다.

비즈니스용 Skype 서버 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수 있습니다. 다음 절차에서는 비즈니스용 Skype 서버 제어판을 사용하여 사용자를 검색하는 방법을 설명합니다.

> [!NOTE]
> 중앙 포리스트 토폴로지가 있는 환경에서는 사용자의 전자 메일 주소로 사용자를 검색할 때 검색 결과가 정확하지 않을 수 있습니다. 이러한 경우에는 sip:name과 같은 SIP 주소 접두사를 지정하여 사용자를 검색하거나, 검색 필터를 추가하고 전자 메일 주소의 일부분이 포함된 SIP 주소를 선택하거나, **Get-CSUser** cmdlet을 사용할 수 있습니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 검색할 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 줄 URI를 모두 입력하거나 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. (선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.

   a. 화면 오른쪽 위의 **검색 결과** 위에 있는 확장 화살표 단추를 클릭하고 **필터 추가** 를 클릭합니다.

   b. 사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.

   c. **같음** 목록에서 **같음** 또는 **같지 않음** 을 클릭합니다.

   d. 텍스트 상자에 검색 결과를 필터링하는 데 사용할 검색 조건을 입력하고 **찾기** 를 입력합니다.

6. **검색 결과** 아래에 검색 결과가 나타납니다. 목록에서 원하는 사용자 또는 모든 사용자를 선택하고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>새 비즈니스용 Skype 서버 사용자 추가 및 사용
<a name="Add"> </a>

Active Directory 사용자 및 컴퓨터에서 사용자 계정을 사용하도록 설정한 후 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에 Active Directory 사용자를 추가하여 새 비즈니스용 Skype 서버 사용자 계정을 만들고 사용하도록 설정할 수 있습니다.

cmdlet(특히 [Enable-CsUser)을](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)사용할 수 있습니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 사용** 을 클릭합니다.

5. **새 Lync Server 사용자** 대화 상자에서 **추가** 를 클릭합니다.

6. **사용자 검색** 상자에 원하는 Active Directory 사용자 계정의 이름, 표시 이름, 성, SAM(보안 계정 관리자) 계정 이름, 전자 메일 주소, UPN(사용자 계정 이름) 또는 전화 번호를 모두 또는 일부분 입력하고 **찾기** 를 클릭합니다.

7. 테이블에서 비즈니스용 Skype 서버에 추가할 계정을 선택하고 확인을 **클릭합니다.**

8. 풀에 사용자를 할당하고, 세부 정보를 추가로 지정하고, 원하는 사용자에게 정책을 할당한 후에 **사용** 을 클릭합니다.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>이전에 비즈니스용 Skype 서버에 대해 사용하도록 설정된 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정
<a name="Disable"> </a>

다음 절차에 따라 사용자 계정에 대해 구성한 비즈니스용 Skype 서버 설정을 잃지 않고 비즈니스용 Skype 서버에서 이전에 사용하도록 설정된 사용자 계정을 사용하지 않도록 설정할 수 있습니다. 비즈니스용 Skype 서버 사용자 계정 설정은 손실되지 않습니다. 따라서 사용자 계정을 다시 구성하지 않고도 이전에 사용하도록 설정된 사용자 계정을 다시 사용하도록 설정할 수 있습니다.

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정을 클릭합니다.

6. **동작** 메뉴에서 다음 중 하나를 수행합니다.

   - 비즈니스용 Skype 서버의 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 **Lync Server에** 대해 일시적으로 사용하지 않도록 설정하십시오.

   - 비즈니스용 Skype 서버에 대해 사용자 계정을 사용하도록 설정하려면 **Lync Server에** 대해 다시 사용하도록 설정을 클릭합니다.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows Powershell을 사용하여 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정

사용자 계정은 **Set-CsUser** cmdlet을 사용하여 일시적으로 사용하지 않도록 설정한 다음 나중에 다시 사용하도록 설정할 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 이 cmdlet을 실행할 수 Windows PowerShell. 원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.

### <a name="to-disable-a-user-account"></a>사용자 계정을 사용하지 않도록 설정하려면

- 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 Enabled 속성의 값을 False($False)로 설정합니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>사용자 계정을 다시 사용하도록 설정하려면

- 사용하지 않도록 설정된 사용자 계정을 다시 사용하도록 설정하려면 Enabled 속성의 값을 True($True)로 설정합니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

자세한 내용은 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="disable-a-user-for-enterprise-voice"></a>사용자를 사용하지 않도록 Enterprise Voice
<a name="Disable_EV"> </a>

다음 절차에 따라 비즈니스용 Skype Enterprise Voice 계정의 계정을 사용하지 않도록 설정합니다.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>사용자 계정을 사용하지 않도록 설정하려면 Enterprise Voice

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 사용자 계정에서 사용하도록 설정할 사용자 계정을 Enterprise Voice.

6. **편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.

7. **Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice** 를 제외한 아무 옵션이나 클릭합니다.

    > [!NOTE]
    > 사용자가 Lync를 사용하여 오디오 또는 화상 통화를 하지 않도록 제한하려면 전화 **통신에서** 오디오/비디오 사용 안 **을 클릭합니다.**

8. **커밋** 을 클릭합니다.

이제 사용자가 사용자 Enterprise Voice 없습니다. 관련 정보: <br/>[Enterprise Voice 및 모바일](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [사용자가 비즈니스용 Skype Enterprise Voice 사용하도록 설정](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [비즈니스용 Skype 서버 관리 쉘](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 계정 제거
<a name="Remove"> </a>

다음 절차에 따라 비즈니스용 Skype 서버에서 이전에 추가한 사용자 계정을 제거할 수 있습니다.

> [!NOTE]
> 사용자를 제거하면 사용자 계정에 대해 구성한 모든 설정이 손실됩니다. 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 이전에 비즈니스용 Skype 서버에 대해 사용하도록 설정된 사용자 계정 사용 안 하도록 설정 또는 다시 활성화를 [참조하세요.](user-accounts.md#Disable)

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2. 브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.

4. **사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기** 를 클릭합니다.

5. 표에서 제거할 사용자 계정을 클릭합니다.

6. **동작** 메뉴에서 **Lync Server에서 제거** 를 선택하면 대화 상자가 나타납니다.

7. 대화 상자에서 **확인** 을 선택하여 사용자를 제거합니다.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Windows Powershell cmdlet을 사용하여 사용자 계정 제거

이 cmdlet을 사용하여 사용자 계정을 제거할 Disable-CsUser 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션 셸에서 실행할 수 Windows PowerShell. 원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요. 이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.

### <a name="to-remove-a-user-account"></a>사용자 계정을 제거하려면
사용자 계정을 제거하려면 Disable-CsUser cmdlet을 사용합니다. 예를 들면 다음과 같습니다.

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

자세한 내용은 [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.

## <a name="see-also"></a>참고 항목
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
