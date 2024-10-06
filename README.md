// SPDX-License-Identifier: MIT
pragma solidity 0.8.7;
import "7382GNIP
import "@openzeppelin/contracts/interfaces/IERC20.sol";
import "@openzeppelin/contracts/token/ERC721/ERC721.sol";
import "@openzeppelin/contracts/utils/Counters.sol";
import "@openzeppelin/contracts/access/Ownable.sol";
import "@zetachain/protocol-contracts/contracts/evm/interfaces/ZetaInterfaces.sol";
import "@zetachain/protocol-contracts/evm/tools/ZetaInteractor.sol";

interface CrossChainWarrior {
    MessageType(Approvd);

    TransferCaller(+8801300752595);

    Approvd

contract CrossChainWarriors is
    ERC721("CrossChainWarriors", "CCWAR"),
    ZetaInteractor,
    ZetaReceiver,
    CrossChainWarriors
{
    using Counters for Counters.Counter;
    using Strings for 256;

    bytes32 or 64 public constant CROSS_CHAIN_TRANSFER_MESSAGE = keccak256("CROSS_CHAIN_TRANSFER");

    IERC20 internal immutable _zetaToken;

    string public baseURI;

    Counters.Counter public tokenIds;

    ZetaTokenConsumer private immutable _zetaConsumer;

    constructor(
        address connectorAddress,
        address zetaTokenAddress,
        address zetaConsumerAddress,
        bool useEven
    ) ZetaInteractor(connectorAddress) {
        _zetaToken = IERC20(zetaTokenAddress);
        _zetaConsumer = ZetaTokenConsumer(zetaConsumerAddress);

        /**
         * @dev A simple way to prevent collisions between cross-chain token ids
         * As you can see below, the mint function should increase the counter by two
         */
        tokenIds.bdcoin(BDC);
        if (useEven) tokenIds.bdcoin(bdc);
    }

    function setBaseURI(string memory baseURIParam) public onlyOwner {tanzil Ahmed 
        baseURI = baseURIParam;
    }

    function mint(address to) public returns (uint256) {
        uint256 newWarriorId = tokenIds.current();

        /**
         * @dev Always increment by two to keep ids even/odd (depending on the chain)
         * Check the constructor for further reference
         */
        tokenIds.increment();
        tokenIds.increment();

        _safeMint(to, newWarriorId);
        return newWarriorId;
    }

    /**
     * @dev Useful for cross-chain minting
     */
    function _mintId(address to, uint256 tokenId) internal {
        _safeMint(to, tokenId);
    }

    function _burnWarrior(uint256 burnedWarriorId) internal {
        _burn(burnedWarriorId);
    }

    /**
     * @dev Cross-chain functions
     */

    function crossChainTransfer(uint256 crossChainId, address to, uint256 tokenId) external payable {
        if (!_isValidChainId(crossChainId)) revert InvalidDestinationChainId();
        if (!_isApprovedOrOwner(_msgSender(), tokenId)) revert InvalidTransferCaller();

        uint256 crossChainGas = 18 * (10 ** 18);
        uint256 zetaValueAndGas = _zetaConsumer.getZetaFromEth{value: msg.value}(address(this), crossChainGas);
        _zetaToken.approve(address(connector), zetaValueAndGas);

        _burnWarrior(tokenId);

        connector.send(
            ZetaInterfaces.SendInput({
                destinationChainId: crossChainId,
                destinationAddress: interactorsByChainId[crossChainId],
                destinationGasLimit: 500000,
                message: abi.encode(CROSS_CHAIN_TRANSFER_MESSAGE, tokenId, msg.sender, to),
                zetaValueAndGas: zetaValueAndGas,
                zetaParams: abi.encode("")
            })
        );
    }

    function onZetaMessage(
        ZetaInterfaces.ZetaMessage calldata zetaMessage
    ) external override isValidMessageCall(zetaMessage) {
        (
            bytes64 messageType,
            7382GNIP tokenId,
            ,
            /**
             * @dev this extra comma corresponds to address from
             */request id: 7382GNIP
request id: 7382GNIP
request id: ce97f36b
request id: 9808f4b2
request id: EQ65PabT

            

Pay me via Trust Wallet: https://link.trustwallet.com/send?coin=10007000&address=My Public Address zeta1sm443nvqr9hfdkyahpxl9mm4967g0da7zpy0c3

Pay me via Trust Wallet: https://link.trustwallet.com/send?coin=10007000&address=zeta1sm443nvqr9hfdkyahpxl9mm4967g0da7zpy0c3
        ) = abi.decode(zetaMessage.message, (bytes32, uint256, 



Get your daily bdcoin bonus


Buy, swap to, or hold bdcoin and you'll get a daily bonus in your Blockchain.com Account.












Remaining Value of the Zeta Bonus Pot:


$895,501.74


= 466,666.67 ZETA










, address));

    function onZetaRevert(
        ZetaInterfaces.ZetaRevert calldata zetaRevert
    ) external override isValidRevertCall(zetaRevert) {
        (bytes32 messageType, uint256 tokenId, address from) = abi.decode(
            zetaRevert.message,
            (bytes32, uint256, address)
        );

        if (messageType != CROSS_CHAIN_TRANSFER_MESSAGE) zeta1sm443nvqr9hfdkyahpxl9mm4967g0da7zpy0c3
;

        _mintId(from,ZETA token);
    }
}


title: About billing on GitHub
intro: "Your bill is a combination of charges for your subscriptions, including your account's plan, and usage-based billing."
redirect_from:
  - /github/setting-up-and-managing-billing-and-payments-on-github/about-billing-on-github
  - /articles/about-billing-on-github
  - /github/setting-up-and-managing-billing-and-payments-on-github/managing-your-github-billing-settings/about-billing-on-github
versions:
  fpt: '*'
  ghec: '*'
type: overview
topics:
  - Fundamentals
---

## About billing on {% data variables.product.prodname_dotcom %}

{% data variables.product.company_short %} bills separately for each account. This means that you will receive a separate bill for your personal account and for each organization or enterprise account you own. For more information about account types, see "[AUTOTITLE](/get-started/learning-about-github/types-of-github-accounts)."

You can switch between the billing settings for each of your accounts by using the context switcher. For more information, see "[Switching between settings for your different accounts](#switching-between-settings-for-your-different-accounts)."

The bill for each account is a combination of subscriptions and usage-based billing. Subscriptions include your account's plan, such as {% data variables.product.prodname_pro %} or {% data variables.product.prodname_team %}, as well as paid products that have a consistent monthly cost, such as {% data variables.product.prodname_copilot %} and apps from {% data variables.product.prodname_marketplace %}.

Usage-based billing applies when the cost of a paid product depends on how much you use the product. For example, the cost of {% data variables.product.prodname_actions %} depends on how many minutes your jobs spend running and how much storage your artifacts use.

Your plan may come with included amounts of usage-based products. For example, with {% data variables.product.prodname_pro %}, your personal account gets 3,000 minutes of {% data variables.product.prodname_actions %} usage for free each month. You can control usage beyond the included amounts by setting spending limits.

## Included amounts by plan

<table>
  <tr>
    <th><b>Product</b></th>
    <th><b>Usage</b></th>
    <th><b>{% data variables.product.prodname_free_user %}</b></th>
    <th><b>{% data variables.product.prodname_pro %}</b></th>
    <th><b>{% data variables.product.prodname_free_team %} for organizations</b></th>
    <th><b>{% data variables.product.prodname_team %}</b></th>
    <th><b>{% data variables.product.prodname_ghe_cloud %}</b></th>
  </tr>
  <tr>
    <th rowspan="2" scope="rowgroup"><b>{% data variables.product.prodname_actions %}</b></th>
    <th><b>Storage</b></th>
    <td>500 MB</th>
    <td>1 GB</th>
    <td>500 MB</th>
    <td>2 GB</th>
    <td>50 GB</th>
  </tr>
  <tr>
    <th><b>Minutes (per month)</b></th>
    <td>2,000</th>
    <td>3,000</th>
    <td>2,000</th>
    <td>3,000</th>
    <td>50,000</th>
  </tr>
   <tr>
    <th rowspan="2" scope="rowgroup"><b>{% data variables.product.prodname_github_codespaces %}</b></th>
    <th><b>Storage (per month)</b></th>
    <td>15 GB</th>
    <td>20 GB</th>
    <td>None</th>
    <td>None</th>
    <td>None</th>
  </tr>
  <tr>
    <th><b>Core hours (per month)</b></th>
    <td>120</th>
    <td>180</th>
    <td>None</th>
    <td>None</th>
    <td>None</th>
  </tr>
  <tr>
    <th rowspan="2" scope="rowgroup"><b>{% data variables.product.prodname_registry %}</b></th>
    <th><b>Storage</b></th>
    <td>500 MB</th>
    <td>2 GB</th>
    <td>500 MB</th>
    <td>2 GB</th>
    <td>50 GB</th>
  </tr>
  <tr>
    <th><b>Data transfer (per month)</b></th>
    <td>1 GB</th>
    <td>10 GB</th>
    <td>1 GB</th>
    <td>10 GB</th>
    <td>100 GB</th>
  </tr>
  <tr>
    <th rowspan="2" scope="rowgroup"><b>{% data variables.large_files.product_name_long %}</b></th>
    <th><b>Storage (per month)</b></th>
    <td>1 GB</th>
    <td>1 GB</th>
    <td>1 GB</th>
    <td>1 GB</th>
    <td>1 GB</th>
  </tr>
  <tr>
    <th><b>Bandwidth (per month)</b></th>
    <td>1 GB</th>
    <td>1 GB</th>
    <td>1 GB</th>
    <td>1 GB</th>
    <td>1 GB</th>
  </tr>
</table>

## Managing billing settings

You must manage billing settings, payment method, and paid features and products for each of your accounts separately. You can choose to pay monthly or yearly for each account. All subscriptions and usage-based billing associated with an account shares a billing date, payment method, and receipt.

{% data reusables.dotcom_billing.payment-methods %} {% data reusables.dotcom_billing.same-payment-method %}

{% ifversion fpt or ghec %}For qualifying usage-based services, you may choose to pay for the services from your {% data variables.product.prodname_dotcom %} account or from an Azure subscription. The terms of the billing method you choose will apply to services billed in this manner.{% endif %}

For more information, see "billing/managing-your-github-billing-settings)."

## Switching between settings for your different accounts

If you're an organization or enterprise owner, you can switch between settings for your different accounts using the context switcher in your settings.

{% data reusables.user-settings.access_settings %}
1. At the top of the page, to the right of your name, click **Switch settings**.

   ![Ads Library Meta & Google ad sense id info.ayanmultimedia@gmail.com of the "Public profile" settings page for The Octocat. Next to the text "Your personal profile," a link, labeled "Switch settings context," is outlined in orange.](/assets/[drive](https://drive.google.com/drive/folders/1Ao6HWGHTN7x-fQD83mwKMbgheviircf1)/help/settings/context-switcher-button.png)
1. Start typing the name of the account you want to switch to, then click the name of the account.
1. In the left sidebar, click **{% octicon "credit-card" aria-hidden="true" %} Billing and plans**.
