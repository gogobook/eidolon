source 'https://github.com/CocoaPods/Specs.git'
source 'https://github.com/artsy/Specs.git'

plugin 'cocoapods-keys', {
  :project => 'Eidolon',
  :keys => [
    'ArtsyAPIClientSecret',
    'ArtsyAPIClientKey',
    'HockeyProductionSecret',
    'HockeyBetaSecret',
    'MixpanelProductionAPIClientKey',
    'MixpanelStagingAPIClientKey',
    'CardflightProductionAPIClientKey',
    'CardflightProductionMerchantAccountToken',
    'StripeProductionPublishableKey',
    'CardflightStagingAPIClientKey',
    'CardflightStagingMerchantAccountToken',
    'StripeStagingPublishableKey'
  ]
}

platform :ios, '9.0'
use_frameworks!

# Yep.
inhibit_all_warnings!

target 'Kiosk' do

  # Artsy stuff
  pod 'Artsy+UIColors'
  pod 'Artsy+UILabels'
  pod 'Artsy-UIButtons'

  if ['orta', 'ash', 'artsy', 'Laura', 'alan', 'CI', 'distiller', 'travis'].include?(ENV['USER'])
      pod 'Artsy+UIFonts', '~> 1.1.0'
  else
      pod 'Artsy+OSSUIFonts', '~> 1.1.0'
  end

  pod 'ORStackView', '2.0'
  pod 'FLKAutoLayout', '0.1.1'
  pod 'ARCollectionViewMasonryLayout', '~> 2.0.0'
  pod 'SDWebImage', '~> 3.7'
  pod 'SVProgressHUD'

  pod 'ARAnalytics/Mixpanel'
  pod 'ARAnalytics/HockeyApp'

  pod 'CardFlight'
  pod 'Stripe'
  pod 'ECPhoneNumberFormatter'
  pod 'UIImageViewAligned', :git => 'https://github.com/ashfurrow/UIImageViewAligned.git'
  pod 'DZNWebViewController', :git => 'https://github.com/orta/DZNWebViewController.git'
  pod 'Reachability', :git => 'https://github.com/ashfurrow/Reachability.git', :branch => 'frameworks'

  pod 'UIView+BooleanAnimations'
  pod 'ARTiledImageView'
  pod 'XNGMarkdownParser'
  pod 'ISO8601DateFormatter'

  # Swift pods
  pod 'SwiftyJSON'
  pod 'RxSwift'
  pod 'RxCocoa'
  pod 'Moya/RxSwift', '8.0.0-beta.3'
  pod 'NSObject+Rx'
  pod 'Action'

  target 'KioskTests' do
    inherit! :search_paths

    pod 'FBSnapshotTestCase'
    pod 'Nimble-Snapshots'
    pod 'Quick'
    pod 'Nimble'
    pod 'Forgeries'
    pod 'RxBlocking'

  end
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['SWIFT_VERSION'] = '3.0'
            config.build_settings['MACOSX_DEPLOYMENT_TARGET'] = '10.10'
        end
    end
end
