Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/xenial64'

  config.vm.network 'private_network', ip: '172.16.0.5'

  ansible_extra_vars = {}

  config.vm.provision(
    :ansible,
    playbook: 'playbooks/elk.yml',
    groups: {elk: %w(default)},
    verbose: '-vvv',
    raw_arguments: %w(--diff --become),
    extra_vars: ansible_extra_vars
  )
end
