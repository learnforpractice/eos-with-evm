if( EOSIO_COMPILE_TEST_CONTRACTS )
   add_contract( test_eth_account test_eth_account main.cpp ${CMAKE_SOURCE_DIR}/../../externals/aleth/evm4eos/eth_account.cpp )

   target_compile_definitions(test_eth_account PRIVATE USE_INTRINSIC_EVM_RECOVER_KEY USE_INTRINSIC_EVM_GET_ACCOUNT_ID USE_INTRINSIC_EVM_EXECUTE)

   target_include_directories(test_eth_account PRIVATE 
      PRIVATE ${CMAKE_SOURCE_DIR}/../../externals/aleth/evm4eos
   )

else()
   # configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/noop.wasm ${CMAKE_CURRENT_BINARY_DIR}/noop.wasm COPYONLY )
   # configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/noop.abi  ${CMAKE_CURRENT_BINARY_DIR}/noop.abi  COPYONLY )
endif()
